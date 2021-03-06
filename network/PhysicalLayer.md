# Phisical Layer

## 1. 물리 계층이란
물리적인 communication을 위한 protocol이 존재한다.  
그러므로 data link 계층으로 부터 온 데이터를 물리 계층에서 전환된다.  

## 2. Analog and digital signal
- 1.Data
    - 1. analog data : 연속적인 성격을 가진 데이터
        - ex) 아날로그 시계, 사람의 목소리
    - 2. digital data : 0과 1로 연속되지 않은 데이터
        - ex) 디지털 시계
- 2.Signal
    - 1. analog
        - 무한의 값이 많은 value를 갖는다.
         ![analog](./image/physical/analog.png)
    - 2. digital
        - 제한된 value값을 갖는다.
        - 0과 1로 표현된다.
         ![sine wave](./image/physical/digital.png)

## 3. Periodic and Nonperiodic
- 1. Periodic signal(주기적)
    - 특정 시간(period) 동안 패턴을 만든다.
    - simple periodic analog signal 
        - sine wave 
    - Composite periodic analog signal
        - 복수의 sine wave로 구성된다.
- 2. sine wave
  ![sine wave](./image/physical/sinewave.png)
    일정 기간동안 특정 패턴을 갖는다.
    

    - Peak Amplitude
    ![Amplitude](./image/physical/amplitude.png)
        - peak amplitude 높으면 목소리도 높다.
    
    -  sine wave의 특징
        - Period(T) : 1 cycle이 완료되는 시간.
        - Frequency(f) : 1 초 동안  period의 수.
        - f = 1 / T
        - T = 1 / F 로 표현 가능하다.
        - 비교 
        ![short](./image/physical/short.png)
            - 1초에 12의 period가 존재하므로 
            - period : 1/12 s, 12Hz이다.
            - peroid가 많아지면 high frequency이고, period가 작아진다.
        ![long](./image/physical/long.png)
            - 1초에 6개의 peroid가 존재하므로
            - peroid : 1/6 s, 6Hz이다.
            
        - Phase
        wave form이 시작할때의 position을 의미한다.
         ![phase](./image/physical/phase.png)

    sine wave를 정의하는 것은 amplitude, frequency, phase로 총 3가지 이다.  
    표현 하는 방식으로는 ```time domain plot```과 ```frequency domain plot```이 존재한다.

    1. time domain plot
    ![phase](./image/physical/timedomain.png)
        - time을 x축으로 하기 때문에 보기 편하다.
        - 하지만 복잡해지면 알아보기 힘들다.
    2. frequency domain plot
    ![phase](./image/physical/frequencydomain.png)
        - 익숙하지 않아 불편하지만, 위의 것을 간단하게 나타낸다.
    3. 위의 예를 보자.
    ![복잡](./image/physical/multi.png)
    - 첫번째 그림은 한번에 3개의 sinewave를 나타내기 때문에 굉장히 복잡한 반면
    ![간단](./image/physical/easy.png)
    - 두번째 그림으로 frequency 기준으로 그리면 간단해진다.

- 3. Composite Signals
    많은 simple sine wave들로 인해 구성된다.
    - Fourier analysis : 어떤 composite signal은 다른 frequency,amplitude, phase를 가진 sine wave의 조합이다.
    - composite signal 또한 periodic 과 non-periodic이 존재한다.
    - 예제1 : Periodic  

    ![첫번째](./image/physical/one.png)
        - 위의 그림은 복잡하지만 연속된 신호(**periodic somposite signal**)이다.  
        - 여러 simple sinewave가 합쳐진 것이다.

    ![두번](./image/physical/two.png)
        - 첫번째 그림의 것을 여러개의 simple sine wave로 표현한 것이다.

          
    - 예제2 : non-periodic  

    ![세번](./image/physical/three.png)
    - 위의 그림은 **nonperiodic somposite signal**이다.
    - 오른쪽의 그림은 f 밑의 신호들은 너무 작기 때문에 잘라버리고 사용하지 않는다.

    amplitude
- 3. Nonperiodic signal(비주기적)
    - 패턴 없이 바뀐다. 
    


## 4.Bandwidth
복잡한 신호(composite signal)안에 주파수의 범위를 bandwidth라고 한다.  BPS(Bit Per Second)로 표현한다.
Badnwidth =  (가장 높은 주파수) - (가장 낮은 주파수)  
Bandwidth가 높을 수록, 많은 데이터를 보낼 수 있고 빠르다.
참고
- AM 라디오 주파수범위는 530 ~ 1700kHz이다.
- FM 라디오 주파수 범위는 88 ~ 108 MHz이다.
- 그러므로 FM 라디오에서 데이터를 많이 보낼 수 있다.
![세번](./image/physical/bandwidth.png)
    
## 5.Digital Signals
컴퓨터는 바이너리 연산을 하기 때문에, 디지털 신호(0,1)로 사용해야한다.
- 1. 디지털 신호가 L Level을 같는다면, Log2L이 필요하다.
![l2](./image/physical/l2.png)
- 위의 그림은 1개의 비트를 사용하여 2개의 level이 존재한다.
![l4](./image/physical/l4.png)
- 위의 그림은 2개의 비트를 사용하여 4개의 Level이 존재한다.
- 1비트보다 더 많이 데이터를 보낼 수 있으므로 전송속도가 빨라진다.
- 예제
    - 1.9 레벨의 디지털 신호가 있다면, 몇개의 비트가 필요한가 ?
        - Log2의 9를 계산해 보면, 3.17 bit이다. 그러므로 최소 4비트가 필요하다.
### Bit Rate
Bit Per Second(BPS)를 의미한다. 1초에 몇 bit를 보낼 수 있는지
- 1. 예제
    - 한 페이지에 24줄이 들어가고, 한 줄엔 80개의 character가 들어간다. 총 100페이지를 1초에 보내기 위해서 얼만큼의 bitrate가 필요한가
        - 100(page)* 24(lines) * 80(char) * 8(bits per char) = 1,536,000 bps = 1.536 Mbps
    - HDTV(1920 x 1080 pixels)rk 1초에 30번 스크린을 바꾼다면, 얼만큼의 bit rate가 필요한가? (한 픽셀의 색을 나타내기 위해 24 bits 사용)
        - 1920 x 1080 x 30(screens) x 24(bits per one pixel) = 1,492,992,000 = 1.5Gbps

### Bit Length
wavelength란 한 사이클이 transmission medium을 점유하는 길이 이다. 주기라고도 하며, 한 cycle 의 길이이다. 
**bit length**란 한 bit가 transmission medium을 점유하는 길이 이다.

- 1.현실 세계의 데이터 통신에서  비주기적 디지털 신호가 발생하다고 생각해보자.
    - 디지털 신호를 다른 목적지 까지 전달하는 방법은 2가지가 있다.
        - ***Baseband transmission***
        - **Broadband transmission***
    - 밑에 넘어가기에 앞서, 모든 통신의 기본은 **아날로그**라는 것을 알아두자
- 2.Baseband transmission
![baseband](./image/physical/baseband.png)
    - 디지털 신호를 아날로그로 변환하지 않는다.
    - low-pass channel이 필요하다.
        - bandwidth가 0부터 시작하는 채널이다.(이런 경우 절대 없다.)
        - low-pass channel은 ***wide bandwidth*** 와 ***limited(narrow) bandwidth*** 가 존재한다.

    - Low-pass channel, wide bandwidth
            ![wide](./image/physical/wide.png)
             0부터 시작, 넓은 대역을 사용한다.
            ![baseband2](./image/physical/baseband2.png)
            이 곳에선 low-pass channel이 무한대의 badnwidth를 가진다고 가정해보자.(불가능함.)
            위의 그림을 보면 목적지에 도착한 신호는 왜곡으로 인해 손상된다.
            그러므로 분석을 해서 유추를 해내어 아날로그 신호로 변환한다.  
       
    - Low-pass channel narrow bandwidth
            ![narrow](./image/physical/narrow.png)
             0부터 시작, 한정된 대역을 사용  
             wide는 실제로 굉장히 비용이 많이 들기 때문에 불가능하다.  
             대략젹으로 유추하는 방법으로는 **Rough Approximation** 과 **Better Approximation** 방법이 있다.  
        - Rough Approximation
        ```도저히 이해를 못하겠음 물어봐야됨.```
        - Better Approximation
        주파수에 harmonics를 더해 bandwidth를 증가 시킨다.(N/2,3N/2,5N/2)
        ![better](./image/physical/better.png)
        ![better](./image/physical/better2.png)
            - bits를 빨리 보내기 위해선 더 넓은 bandwidth가 필요하다.
    
- 3.Broadband transmission(modulation)
![broadband](./image/physical/broadband.png)
    - 디지털 신호를 아날로그 신호로 변환한다.
    - band-pass channel을 사용한다.
        - bandwidth가 0부터 시작하지 않는다.(이게 현실세계의 특징.)

    ![broadband2](./image/physical/broadband2.png)
    - in band-pass channel
        - 1.디지털 신호를 composite아날로그 신호로 변환.
        - 2.single-frequency analog signal 이용
        - 3.carrier의 amplitude가 디지털 신호 처럼 보이게 변환됨.
        - 4.리시버는 받으면 디지털 신호로 변환
        - 5.결과는 원본의 복제와 같다.

## 6. Transmission Impairment
신호들은 link를 통해 이동하면서 손상되고, link의 불완전성이 impairment를 만든다. 원인으로 3가지가 존재한다.
- attenuation  
    - 에너지의 손실을 의미한다. 신호의 전기에너지는 저항으로 인해 열이 발생한다. 그렇기 때문에 신호는 약해지고, 중간에서 amplifiers를 사용하여 신호를 증폭시킨다.
    - ![attenuation](./image/physical/attenuation.png)
    - 하지만 증폭과 동시에 noise 또한 증폭을 시키기 때문에, repeator를 사용하여 noise를 제거하는 방법을 사용한다.
    - attenuation은 Decibel을 사용하여 표현한다. 이 표현은 상대적인 표현이기 때문에, 시작과 끝을 의미하는 P1, P2를 이용하여 구한다.
    - ![attenuation](./image/physical/attenuation1.png)
    - (-) 는 lose(attenuated) : negative
    - (+) 는 gain(amplified) : positive
    - 예제 1
        - 신호를 transmission medium을 통해 보내지만 반 감소한다고 가정하자. 이는 P2 = 0.5*P1을 의미 하므로, 값을 구해보면 아래와 같다.
    - ![ex](./image/physical/ex1.png)

    -  ![ex2](./image/physical/ex2.png)
    - 위의 그림은 Transmission medium을 통해 전달되면서 발생하는 감쇄현상을 emplifier를 통해 증폭시켜 처음에 보내려면 1 dB를 만들어주는 현상이다.
    - 예제 2
        - 가끔 dB는 signal power를 측정하기 위해 milliwatts를 사용한다. 이 상황에서 dBm = 10 log(10)Pm(Pm은 milliwatts)이라면, dBm = -30일때의 signal pwoer를 구하면 아래와 같다.
        - ![ex3](./image/physical/ex3.png)
    - 예제 3
        - 케이블 안에서 손실을 deibels per kilometer(dB/km)로 정의된다. 시작할때 -0.3 dB/km의 손실을 갖는 케이블에 2mW의 파워를 갖는다면, 5km일때 signal power를 구하라.
        - 케이블에서 손실을 구하면 -0.3 * 5 = -1.5 dB이다.
        - ![ex4](./image/physical/ex4.png)
- distortion(왜곡)
    - 신호의 모양이 변하는 현상이다.
    - 각 신호들은 미디어를 이용하여 목적지 까지 가는데 각자 다른 딜레이가 있는데, 그 딜레이로 인해 phase가 변하게 된다.
    - ![sender](./image/physical/sender.png)
    - ![receiver](./image/physical/receiver.png)

- noise(가장 많이 나타나므로 핵심적인 문제이다.)
    - thermal noise : 저항으로 인해 생기는 변형
    - induced noise : 모터에서 모터의 특징으로 인해 생기는 변형
    - crosstalk : 합선으로 인한 변형
    - impulse noise : 스파크로 인해 변형
    - ![noise](./image/physical/noise.png)
        - 위의 그림은 noise로 인해 신호가 변형되는 모습을 보여준다.
    
- Signal-to-Noise Ratio(**SNR**) = average signal power / average noise power
    - 밑의 그림은  noise를 받았을때 amplitude에 따라 변형되는 모습이 어떤지 보여준다.
    - ![noise2](./image/physical/noise2.png)
        - 위의 그림을 보면 amplitude가 클수록, noise가 있을떄 데이터를 무사히 보낼 수 있음을 나타낸다. 
        - 이를 위의 식을 사용해서 생각해보면, 동일한 noise에 signal power(amplitude)가 커지면, SNR을 커지고, 이는 Robust하게 전송할 수 있다는 것을 의미한다.

    - High SNR : less corrupted signal
    - Low SNR : more corrupted signal by noise
    - SNR dB는 데시벨로 표현되고 아래와 같이 사용한다.
    - ![SNR](./image/physical/SNR.png)
    
    - 예제 1
        - 신호의 파워는 10mW이고, noise 의 파워는 1마이크로W이다. SNR의 값과 SNR dB의 값을 구하라.
        - ![SNR](./image/physical/SNREX1.png)
        
## 7. Data Rate Limits
- data communication에서 전송 속도는 중요하다.
- 전송 속도에 영향을 끼치는 3가지
    - bandwidth
    - level of the signals
    - quality of the channel(the level of noise) : transmission layer에서 데이터가 손상되면 계속해서 재 요청하므로 속도에 영향을 준다.
- data rate를 계산하기 위해 두가지의 방법이 존재한다.
    - Nyquist for noiseless channel : 노이즈가 아예 없을때를 가정한다.
        - 이는 이론적인 최대 bitr ate를 정의한다.
        - ![nyquist](./image/physical/nyquist.png)
        - BitRate를 향상시키기 위해 bandwidth와 Level을 상승 시켜야 하지만, Bandwidth는 사실상 고정이고, level을 변화시켜야한다.
        - 하지만 현실적으로 불가능하고, level이 높을 경우, 손상될 경우 유추가 불가능하다.
        - 예제 1
            - 3000 Hz의 BandWidth를 가진 noiseless channel이 2level로 신호를 전송한다면, 최대 bit rate를 구하라
            - ![bitrate1](./image/physical/bitrate1.png)  
        - 예제 2
            - 우리는 20kHz babndwidth의 noiseless channel로 265 kbps를 보낸다면, 몇 signal level 필요한가?
            - ![bitrate2](./image/physical/bitrate2.png)
    - Shannon for a noisy channel : 노이즈를 포함한다.
        - capacity는 소음이 있다는 것을 고려 했을때 최대의 bit rate를 의미한다.(bps로 표현)
        - ![shannon](./image/physical/shannon.png)
        - bandwidth와 SNR에 따라 비례하지만, bandwidth는 사실상 고정이다.
        - level은 capacity에 영향을 끼치지 않는다.
        - 예제 1
            - 노이즈가 굉장히 큰 체널에 SNR이 거의 0이라고 가정하자. 그 이유는 noise가 너무 강해서 라고 하자. 그렇게 되면 Capacity는 아래와 같이 계산된다.
            - ![shannon2](./image/physical/shannon2.png)
        - 예제 2
             - ![shannon3](./image/physical/shannon3.png)
        - 예제 3
             - ![shannon4](./image/physical/shannon4.png)


- 그래서 실제로 limit과 signal level을 구하기 위해 두가지 방법을 모두 사용한다.
    - shannon capacity는 upper limit을 제공하고
    - Nyquist formual는 signal level을 제공한다.
    - 예제 1
        - ![Q1](./image/physical/Q1.png)

## Performance
- networking에서 QoS(Quality of Service)는 중요한 이슈이다.
- Bandwidth에 영향을 받는다.
- bandwidth in hertz
- bandwidth in bits per second  

## Latency(Delay) 지연
- 한 전체 메시지가 목적지 까지 가는데 걸리는 시간. 시작은 1비트를 보낼때 부터 측정한다.
- Propagation time : 한 비트가 출발지에서 목적지 까지 가는데 걸리는 시간.
    - Propagation time = distance / propagation speed

- Transmission time
    - 전체 메시지가 출발지에서 목적지 까지 가는데 걸리는 시간.
    - transmission time = (message size) / Bandwidth of channel
    - ![latency](./image/physical/latency.png)

## Jitter
- delay에 관련된 문제이다.
- 만약 데이터의 패킷이 서로 다른 latency가지게 되면, 그 데이터를 사용하는 receiver는 time-sensitive 하다.

