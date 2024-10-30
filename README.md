# hmrk 2

![image](https://github.com/user-attachments/assets/f85a1239-ef08-47e4-b542-8b399c994e5a)
시스템의 의미있는 상태를 정의하고 그 중심으로 문제를 푸는 것이 상태공간 방정식의 핵심이라할 수 있다.

상태공간 방정식 설정하기
상태변수를 설정한다.
![image](https://github.com/user-attachments/assets/0f08e127-b848-4143-87d1-c73e78386dc1)
EX1 의 그림에서 물체 M의 운동은 다음과 같이 기술 될 수 있다.
$$\[ 
 M \frac{d^2 y(t)}{dt^2} + b \frac{d y(t)}{dt} + k y(t) = r(t) $
\]$$
이 식에서 상태 변수를 설정하면
x_1(t) = y(t), \quad x_2(t) = \frac{dy(t)}{dt}
\]

we can express the system in terms of these variables as:

\[
\frac{dx_1(t)}{dt} = x_2(t)
\]

\[
\frac{dx_2(t)}{dt} = -\frac{b}{M} x_2(t) - \frac{k}{M} x_1(t) + \frac{1}{M} r(t)
\]
와 같이 된다.

![image](https://github.com/user-attachments/assets/d1b3d1b1-2f74-4f7a-9f77-22204133b9bf)
EX2의 그림의 수식에서 상태변수를 설정하면
\[
x_1(t) = v_c(t), \quad x_2(t) = i_L(t)
\]

### By KCL (Kirchhoff's Current Law)

\[
u(t) = C \frac{dx_1(t)}{dt} + x_2(t) \Rightarrow \frac{dx_1(t)}{dt} = \frac{1}{C} [-x_2(t) + u(t)]
\]

### By KVL (Kirchhoff's Voltage Law)

\[
L \frac{dx_2(t)}{dt} + R x_2(t) - x_1(t) = 0 \Rightarrow \frac{dx_2(t)}{dt} = \frac{1}{L} [x_1(t) - R x_2(t)]
\]

Thus, the equations for \( \frac{dx_1(t)}{dt} \) and \( \frac{dx_2(t)}{dt} \) are:

\[
\frac{dx_1(t)}{dt} = \frac{1}{C} [-x_2(t) + u(t)]
\]

\[
\frac{dx_2(t)}{dt} = \frac{1}{L} [x_1(t) - R x_2(t)]
\]

where the output \( y(t) \) is given by:

\[
y(t) = R x_2(t)
\]

state를 정의하면 미분방정식을 라플라스변환을 통해 현재상태를 파악할 수 있다.
x(t) = e^{At}x(0) + \int_0^t e^{A(t-\tau)}Bu(\tau)d\tau

또한 이뿐만 아니라 함수의 초기상태를 정의하고 입력의 효과를 예상할 수 있게되어 식을 훨씬 의미있게 만들 수 있다.
x(t) = \Phi(t)x(0) + \int_0^t \Phi(t-\tau)Bu(\tau)d\tau

상태 벡터를 통해 연립방정식 꼴의 식을 하나의 식으로 표현 할 수 있다.
  \dot{x}(t) = Ax(t) + Bu(t)

     y(t) = Cx(t) + Du(t)

다차 상태 공간 방정식 의 풀이
### 1차 시스템
\[ 
x(t) = e^{At} x(0) + \int_0^t e^{A(t-\tau)} b u(\tau) d\tau 
\]

### n차 시스템
\[ 
x(t) = \exp(At)x(0) + \int_0^t \exp[A(t - \tau)] B u(\tau) d\tau 
\]

### 상태 공간 표현
\[ 
x(s) = [I - A]^{-1} x(0) + [I - A]^{-1} B U(s) 
\]

### 전이 함수
\[ 
\Phi(s) = [I - A]^{-1} 
\]

### 전이 함수의 라플라스 변환
\[ 
\Phi(t) = \mathcal{L}^{-1} \Phi(s) 
\]

### 최종 해
\[ 
x(t) = \Phi(t) \cdot x(0) + \int_0^t \Phi(t - \tau) b u(\tau) d\tau 
\]
