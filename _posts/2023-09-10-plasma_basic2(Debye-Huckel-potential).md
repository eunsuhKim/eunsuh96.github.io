---
layout: post
title: "플라즈마 기초 공부 2"
date: 2023-09-10
categories: [Plasma]
---
Debye-Huckel potential 


# 배운 내용 정리

The electro-static field or potential is given by 

\[
\bar{\phi}_t(r) = \frac{q_t}{4\pi \epsilon_0 r}\exp(-\frac{r}{\lambda_D})
\]

where \(q_t\) is the charge that changes with time and \(r\) is the distance from the test particle and \(\lambda_D\) is the Debye-length.

The derivation of this formula is the following.

- Equation of motion$($ =momentum equation$)$ for the species \(s\) where \(s\) is a field particle.
\[\begin{equation}m_s \frac{du_s}{dt} = -q_s\nabla\phi - \frac{\nabla p_s}{n_s} - \nu_s m_s u_s\end{equation}\]
\(LHS\): time derivative of momentum \(m_su_s\)
\[\begin{equation}\frac{d(m_su_s)}{dt} = \frac{dm_s}{dt}u_s+m_s \frac{du_s}{dt} = m_s \frac{du_s}{dt}\end{equation}\]
\(RHS\): terms that affect the change of momentum.
- \(-q_s\nabla\phi\) : force
- \( - \frac{\nabla p_s}{n_s}\) : momentum loss by pressure
- \( -\nu_s m_s u_u\) : momentum loss by the friction
- notations
    - \(m_s\) : mass of specific particle
    - \(\q_s\) : charge of the particle
    - \(\phi\) : electric field
    - \(p_s\) : pressure
    - \(\nu_s\) : collision frequency
    - \(k_B\) : the Boltzmann coefficient

> Assumptions
> 

Steady-state(\(LHS\approx 0\)), isothermal(\(\nabla p = k_B \nabla T\cdot n+k_B T\cdot n\approx k_B T\cdot n\)), no friction(\(\text{friction term}\approx 0\)) assumption →

\[\begin{equation}0\approx -q_s\nabla \phi - \frac{k_B T_s \nabla n_s}{n_s}\end{equation}\]

where \(T_s\) is the temperature of the species \(s\).

> Boltzmann relation
> 

\[n_s = n_{s0}\exp(-\frac{q_s\phi}{k_BT_s})\]

Weak interaction →

\[\begin{equation}n_s\approx n_{s0}(1-\frac{q_s\phi}{k_B T_s})\end{equation}\]

Assuming weak interaction, the Taylor expansion of this exponential function can be sufficiently precisely approximated by only the 1st order approximation, i.e., Linearization.

> Poisson equation = Gauss’ law for the electric charge
> 

It describes the relation between electric potential and charge density.

\[\begin{equation}-\nabla^2\phi(r) = \frac{ q_T \delta(r)}{\epsilon_0} + \sum_{s} \frac{q_s n_s(r)}{\epsilon_0}\end{equation}\]

- Test particle is very small and thus is regarded as a point: the reason why \(\delta(r)\) is used.
- \(RHS\) contains all the causes.

Boltzmann relation →

\[=\frac{q_T}{\delta(r)}{\epsilon_0}+\sum_{s}\frac{q_s n_{s0}(1-\frac{q_s\phi(r)}{k_B T_s})}{\epsilon_0}\]

Charge neutrality (\sum_s q_s n_{s0}) →

\[ \begin{equation}= \frac{q_T\delta(r)}{\epsilon_0} + \sum_s \frac{n_{s0}q_s^2}{\epsilon_0 k_B T_s}\phi(r)=\frac{q_T\delta(r)}{\epsilon_0} - \sum_{s\in \text{fast enough}}\frac{1}{\lambda_{D_s}}\end{equation}\]

where $ \lambda_{D_s} \equiv ( \frac{\epsilon_0 k_B T_s}{n_{s0} q_s^2} )^2 $

# ChatGPT Q&A result

## Motion equation의 각 항에 관한 설명

1. \(-q_s\nabla \phi\): 
- 전하를 가진 입자가 전기장 내에서 움직일 때, 이 입자에 작용하는 힘은 \(F = q E\)이다. \(E\)는 전기장이고, \(E = - \nabla \phi\)이므로, \(F = -q_s\nabla\phi\)가 된다.
1. \(-\frac{\nabla p_s}{n_s}\):
- 입자는 압력이 높은 지점에서 낮은 지점으로 향하는 힘을 받는다.
- 압력이 균등하게 분포되도록 하는 힘이다.
- 압력 \(p_s\)의 단위는 \([p_s]=\frac{N}{m^2}=Pa\text{(Pascal)}\)이므로, \(\nabla p_s\)의 단위는 \([\nabla p_s]=\frac{\text{(입자 개수)}}{m^3}\) 이다.

<aside>
💡 플라즈마 맥락에서는 보통 압력의 단위로서 $Torr$를 많이 사용하며, $1~Torr$는 대략 $133.322368 Pa$와 같다. 여기서 $Pascal(Pa)$는 SI단위계에서의 압력 단위이며 $1~Pa=1N/m^2$로 정의된다. 그러나 물리량 간의 연산이나 비교를 위해서는 모든 단위를 SI단위계로 변환하는 것이 좋다.

</aside>

- 입자 밀도 \(n_s\)의 단위는 \([n_s]=\frac{\text{(입자 개수)}}{m^3}\)이다.
- 그 결과, \(-\frac{\nabla p_s}{n_s}\)의 단위는 \([-\frac{\nabla p_s}{n_s}]=\frac{N/m^3}{\text{(입자 개수)}/m^3}\), 즉 입자 한 개당 받는 힘을 나타낸다.
1. \(-\nu_s m_s u_s\):
- \(\nu_s\)는 충돌 빈도이다.
- 충돌 빈도 \(\nu_s\)의 단위는 \(\frac{1}{\text{sec}}\)이다.
- 질량 \(m_s\)의 단위는 \(kg\)이다.
- 속도 \(u_s\)의 단위는 \(\frac{m}{sec}\)이다.
- 따라서 \(\nu_s m_s u_s\)의 단위는 \(kg\cdot\frac{m}{sec^2}\), 즉 \(N\text{(뉴턴)}\)이다.
- 이 항은 입자의 운동이 다른 입자와의 충돌로 인한 운동량의 변화율을 나타내며, 결국 힘의 일종이므로 충돌에 의해 입자가 받는 힘을 나타낸다.

## 압력에 관한 식이 성립하는 이유

\[\begin{equation}\nabla p = k_B \nabla T\cdot n+k_B T\cdot n\approx k_B T\cdot n\end{equation}\]

이 식은 \(p=nk_BT\)라는 양변을 공간에 대해 미분한 것이다.

### \(p=nk_BT\)가 성립하는 이유

이상 기체 방정식 \(pV = nRT\)에서

- \(p\)는 압력
- \(V\)는 부피
- \(n\)는 몰 수
- \(R\)은 일반 기체 상수
- \(T\)는 절대 온도

볼츠만 상수 \(k_B\)는 기체 상수 \(R\)과 관련이 있다. 기체 상수는 모든 몰에 대해 일정하며, 볼츠만 상수는 개별 입자에 대해 일정하다. 따라서 다음이 성립한다.

\[R = k_B \cdot N_A~~(N_A:\text{( 아보가드로 수)})\]

이상 기체 방정식을 개별 입자에 대해 쓰면 \(p = \frac{n}{V}k_BT\)가 되며, 여기서 \(\frac{n}{V}\)는 밀도 \(n\)이 된다. 따라서 \(p=nk_BT\)가 된다!

### \(p=nk_BT\)의 단위에 대한 분석

볼츠만 상수 \(k_B\)는 상수여서 단위가 없을 줄 알았더니, 변환을 위해 사용되는 상수여서 그런지 \(J/K\)라는 단위가 있다고 한다. 밀도의 단위 \(1/m^3\)와 온도의 단위 \(K\)와 결합하면 

\[ \begin{equation}
\text{(밀도)} \times \text{(볼츠만 상수)} \times \text{(온도)} = \frac{\text{(입자의 수)}}{m^3} \times \frac{J}{K} \times K 
 = \frac{\text{(입자의 수)} \times J}{m^3} = \frac{J}{m^3}
\end{equation} \]



이 단위는 압력의 단위와 동등하다. 왜냐하면 에너지(\(J\))를 체적(\(m^3\))으로 나눈 것은 힘(\(N\))을 면적(\(m^2\))로 나눈 것과 동일하기 때문이다.

에너지의 단위와 압력의 단위 사이의 관계를 조금 더 살펴 보자.

우선 압력의 정의는 *단위 면적 당 수직으로 작용하는 힘*이다.

일은 에너지와 같은 단위를 가지며, 정의 상 일 \(W\)는 힘 \(F\)과 그 힘 방향으로 이루어진 이동 거리 \(d\)의 곱으로 정의된다:

\[ W= F\times d\] 

이때, 압력이 일정하게 유지되는 경우$($그렇지 않으면 일을 적분으로 계산해야 하는데 지금은 단위를 따지기 위한 과정이므로$)$에는 이 작업은 단위 면적 당 : 

\[ W  = P\times A\times d\]

(\(A\)는 면적이다.)

일의 단위는 \(J\)(줄)이므로 \(N\times m\) 이고 압력의 단위(\(\frac{N}{m^2}\))는 \(\frac{J}{m^3}\)와 같다는 것을 알 수 있다. 일반적으로 압력의 단위를 직접 에너지의 단위로 표현하지는 않지만, 플라즈마 물리학이나 다른 과학 분야에서의 특정 문맥에서는 압력의 gradient를 고려할 때, 에너지 밀도 (\frac{J}{m^3}\)와의 관계를 고려하는 경우가 있다. 

## Boltzmann relation이 성립하는 이유

통계 열역학적으로 특정 에너지 \(E\)를 갖는 분자의 수는 \(\exp(-\frac{E}{k_BT})\)에 비례한다고 한다. (열역학 에너지인 \(k_BT_s\)에 대하여, 에너지 \(E\)를 갖는 상태에 입자가 있을 확률은 
\[ P(E) \propto \exp(-\frac{E}{k_B T_s}) \] 
으로 주어진다. \(k_B\)는 볼츠만 상수이고 \(T_s\)는 절대온도이다.)

또한 전하 \(q_s\)를 갖는 입자가 전위 \(\phi\)에서 얻는 potential 에너지는 \(q_s\phi\)이다. 

- potential energy가 \(q_s\phi\)인 이유
    
    전하가 전기장 내에 위치하게 되면, 그 전하는 potential 에너지를 가지게 된다. 이 potential 에너지는 전하의 크기와 전기장의 강도에 의존한다. 
    
    전하가 위치한 지점의 전위를 \(\phi\)라고 할 때, 그 지점의 전하 \(q_s\)에 의해 발생하는 잠재 에너지 \(U\)는 다음과 같이 정의된다:
    
    \[U= q_s \phi\]
    
    다음은 이 식의 유도 과정이다. 
    
    전기장 \(E\)내에서 작은 거리 \(dx\)를 이동하는 전하 \(q_s\)에 의해 수행되는 일 \(dW\)는 다음과 같다.
    
    \[dW = q_s E dx~~\text{(전기장의 정의인 }E=\frac{F}{q}\text{에 의해서})\]
    
    한편, 전위 \(\phi\)는 전기장 \(E\)와 다음과 같은 관계가 있다.
    
    \[E = - \nabla \phi\]
    
    위 두 식을 결합하면:
    
    \[dW = - q_s\nabla\phi dx\]
    
    전하가 무한한 거리에서 특정 지점까지 이동할 때의 총 일은 전위 \(\phi\)에 의해 주어진 potential 에너지와 같다. 따라서 다음과 같이 전하 \(q_s\)의 potential 에너지 식이 유도된다.
    
    \[U= \int dW = \int - q_s \nabla \phi dx = q_s\phi\]
    
    (\(x\)는 벡터이고, 따라서 potential function의 성질에 따라서 multivariable integration을 하면 나오는 결과인 것 같다.)
    

\(E\)를 대입하면, 전위 \(\phi\)에서의 입자 밀도 \(n_s\)는, \(\phi=0\)에서의 입자 밀도 \(n_{s0}\)에 대하여 다음과 같이 나타난다. (\(\phi=0\)을 대입하면 \(n_{s0}\)가 나오도록)

\[n_s = n_{s0} \exp(-\frac{q_s\phi}{k_BT_s})\]

이를 해석해 보면, 전기장 내에서 charge된 입자의 분포는, 입자의 에너지 분포에 의해 결정된다. 높은 전위에서 입자는 더 높은 potential 에너지를 가지므로, 그 위치에서의 입자 밀도는 더 낮다. 

## Poisson equation에 관한 설명

Poisson equation : \(-\nabla^2 \phi = \frac{\rho}{\epsilon_0}\)

Gauss’ law for electricity : \(\nabla\cdot E = \frac{\rho}{\epsilon_0}\)

- \(\nabla \cdot E\) 는 전기장의 divergence이다.
- \(\rho\)는 전하 밀도이다.
- \(\epsilon_0\)는 진공의 유전율이다.

포아송 방정식은 전하밀도와 전기장 사이의 관계를 표현하는 Gauss’ law for electricity와 동치이다. \(E =-\nabla\phi \)이기 때문이다.

한편 Gauss’ law는 Maxwell의 방정식 네 개 중의 하나로, 전기장과 전하 밀도 사이의 기본적인 관계를 나타낸다. 이는 마치 뉴턴의 제 2법칙 \(F = ma\) 가 힘과 운동상태 사이의 기본적인 관계를 나타내는 것과 비슷한 의미를 가진다. 

이 방정식을 포함한 Maxwell의 방정식들은 전기와 자기에 관련된 수많은 실험 결과들을 기반으로 합리화되었고, 그 결과로 현대 전자기학의 기초가 되었다고 한다.