## 머신러닝이 다루는 정형 데이터(structured data)

전통적인 머신러닝 기반의 기술들로 다룰 수 있는 데이터는 주로 정형데이터입니다.

정형 데이터는 흔히 우리가 '데이터'라는 말들 들었을 때 떠오르는 형태를 생각하시면 됩니다.

데이터 베이스나, 엑셀, CSV 파일 등... 사람이 정제하고 정리한 데이터입니다. 



머신러닝 기반의 기술이란 빅데이터 분석 기법들이라고 생각하시면 됩니다. 주로 R이나 SAS, SPSS같은 통계분석 툴을 활용합니다. 

실수 값 예측에 쓰이는 선형/로지스틱 회귀분석(Linear/Logistic Regression)이라든지,

카테고리 분류에 쓰이는 의사 결정 나무(Decision Tree), 

시계열 예측에 쓰이는 ARMA, ARIMA 모형 등이 대표적입니다. 





## 딥러닝이 다루는 비정형 데이터(unstructured data)

반면 딥러닝 기반의 AI가 다루는 데이터는 비정형 데이터입니다.

비정형 데이터는 사람이 따로 예쁘게 양식을 정리해놓지 않은, 다양한 형식을 가지는 데이터입니다.

일상생활에서 우리가 마주하는, 조금 더 원자료(raw data) 형태에 가까운 데이터이죠.

정형 데이터도 그 수가 꾸준히 늘어나는 추세지만, 비정형 데이터는 기하급수적으로 빠르게 생산되고 있습니다.

2030년이 되면 전체 데이터의 약 90% 이상이 비정형 데이터가 될것이라고 하는데요,

이런 흐름이 나타나기 때문에 다량의 비정형 데이터를 처리하기 위한 딥러닝 기법이 유행하는 게 아닐까 싶습니다. 



## 모라벡의 역설(Moravec's Paradox)

사람에게 쉬운 것이 기계에게는 어렵고, 기계에게 쉬운 것은 사람에게는 어렵습니다.





# 인공신경망(Artificial Neural Network)

딥러닝은 바로 이러한 인간의 사고방식을 기계학습에 녹였습니다.

사람의 사고방식을 기계에 적용하기 위해 컴퓨터공학과 신경과학의 콜라보가 시작됩니다.

## 인공뉴런(Artificial Neuron)

사람이 어떻게 데이터로부터 정보를 얻고 생각을 하는지 알아보기 위해 사람의 신경계를 잠깐 살펴보겠습니다.

사람에게는 ‘뉴런(Neuron)’이라는 신경 세포가 있어서, 세포의 한 쪽(수상돌기)에서 받아들인 전기 자극 정보를 이런 저런 처리를 한 뒤, 다른 쪽 끝(축삭 말단)에서 다음 뉴런로 전달하곤 합니다.

인공 뉴런을 다양한 방식으로 여러 층 쌓아 연결하게 되면 딥러닝의 기본 구조인 **‘인공신경망(Artificial Neural Network)’**이 됩니다.





# Convolutional Neural Network(CNN)

계산가능한 픽셀값으로 이미지 데이터를 읽을 수 있으니 이제는 이미지로부터 정보를 찾아내어 과제를 수행해야겠죠?

이미지란 가로, 세로의 공간적 정보를 담고 있으니 이를 처리하기 위한 특별한 인공신경망 구성 방식이 필요합니다.

여기서 이미지 처리에 특화된 신경망, CNN(Convolutional Neural Network)을 소개해드립니다.

CNN은 이미지로부터 특징을 추출하는 (1) Feature Extraction 영역과, 특정 태스크 수행을 위해 덧붙이는 (2) 태스크 수행 영역 두 가지로 구성되어있습니다.



예를 들어 교통수단으로 탈 것의 사진을 입력받아 그 종류를 자동으로 구별하는 인공지능을 만든다고 가정하겠습니다.

컬러, 외관 골격, 바퀴 모양 등을 파악하는 역할은 (1) 부분이, (1)에서 추출된 정보를 활용하여 탈 것의 카테고리를 K개로 구별하는 역할은 (2)부분이 수행합니다.


![image](https://github.com/jihye-kim11/sp/assets/59490892/4e77d3b5-91ef-4349-8fe3-7a57ed859fea)


특징 추출(Feature Extraction)
이미지로부터 특징을 추출하는 역할은 컨볼루션(Convolution) 연산과 풀링(Pooling) 연산이 수행합니다.

컨볼루션 연산은 컨볼루션 필터(또는 커널)가 입력 이미지를 상하좌우로 훑으며 주요한 특징이 있는지 찾아내는 과정입니다.

컨볼루션 필터를 여러 개 설정하면 그만큼 이미지로부터 다양한 특징을 찾아낼 수 있습니다.

이렇게 찾아낸 결과 특징을 Feature map(또는 convolved feature)라고 부릅니다

특징을 찾는 작업은 이전에 소개드린 인공 뉴런이 하는 일과 마찬가지로, 가중합 + 비선형 함수 적용으로 구성됩니다.



가중합 연산이 어떻게 일어나는지 하나하나 짚어보실 필요는 없습니다. (물론 이해에는 도움이 되겠지만요)

중요한 것은 컨볼루션 연산이 이미지로부터 특징을 추출하는 역할을 한다는 것입니다.



컨볼루션 필터가 이미지를 상하좌우로 훑으며 특징을 찾아낸 뒤, 이 결과로부터 정보를 추리는 풀링 연산이 이어집니다.

풀링 연산은 Feature map을 역시 상하좌우로 훑으며 핵심적인 정보만을 영역별로 샘플링 하는데요,

주로 영역 내 가장 큰 값만을 남기고 나머지 값을 버리는 MaxPooling 방식을 적용합니다.

컨볼루션 연산이 이미지의 특징을 찾아낸다면 풀링 연산은 그 중 핵심정보만 남깁니다.

대부분의 이미지 처리 모델에서는 컨볼루션과 풀링 연산을 여러 번 반복하면서 데이터의 feature를 추려냅니다.

이미지로부터 특징을 배워나가는 작업이라는 뜻에서 이 과정을 'Feature Learning'이라고 부릅니다.



태스크 수행
이미지로부터 주요 특징을 찾아냈다면 이 정보를 활용하여 목표로 하는 태스크를 수행해야 합니다.

이 부분의 구조나 필요한 연산의 종류는 하고자 하는 태스크의 종류에 따라 다릅니다.

이미지 데이터를 처리하는 대표적인 태스크를 몇가지 소개해드리겠습니다.

Classification
입력으로 받은 이미지를 지정된 K개의 클래스(또는 카테고리) 중 하나로 분류하는 과제입니다.

강아지와 고양이를 분류하거나, 공장에서 제품 사진을 보고 양호/불량을 판별하는 업무 등에 쓰일 수 있습니다.


Detection
입력으로 받은 이미지에서 특정 개체가 어디에 위치하는지, (x, y) 좌표값을 찾아주는 과제입니다.

스마트폰으로 사진을 찍을 때 자동으로 인물의 얼굴에 네모박스를 치고 포커스하는 기능을 본 적 있으시죠?

이 경우 얼굴을 detect하는 기능이 탑재되어 있겠네요.

![image](https://github.com/jihye-kim11/sp/assets/59490892/0b810250-d877-458d-8475-6412add6f6d5)


Segmentation
Detection이 네모 박스로 개체를 찾아준다면 Segmentation은 조금 더 정밀하게, 픽셀 단위로 영역을 구별해줍니다.

경계를 잘 찾는 작업은 Detection보다 훨씬 어렵겠죠?
![image](https://github.com/jihye-kim11/sp/assets/59490892/db60e3ba-281e-4263-91fc-2f6691300a2b)




자연어이해(NLU; Natural Language Understanding)
자연어이해, 또는 자연어처리(NLP; Natural Language Processing)라는 말을 많이 들어보셨을겁니다.

말 그대로 자연어를 이해하거나 처리하는 기능에 대한 말인데요, 주체는 '기계'입니다.

기계가 자연어를 이해한다는 것은 어떤걸까요? 명칭에 대해 잠깐 짚고 넘어가겠습니다.

![image](https://github.com/jihye-kim11/sp/assets/59490892/5eab6ff1-9cad-43d0-8679-34174c378fca)

요즘은 자연어 처리(NLP)나 자연어 이해(NLU)라는 용어를 거의 구분없이 사용하고는 있습니다.

하지만 오늘날 인공지능에게 기대하는 것은 단순 규칙에 따른 처리가 아닌, 내용과 맥락을 이해하여 업무를 수행하는 것이므로 '자연어 이해'라는 표현을 이용하도록 하겠습니다.



엄밀히 나누자면 NLP 안에 NLU가 포함됩니다.

NLP에만 해당하는 부분은 언어의 형식, 구문론과 관련된 기능들입니다.

문장을 형태소 단위로 쪼갠다든지(POS), 구문 분석을 수행한다든지 하는 기능입니다.

반면 NLU는 문장 내 표현된 감성은 인식하는 감성분류라든지, 문서 내 중요한 부분을 캐치하는 요약 등의 기능을 포함합니다.



그런데 이마저도 요즘은 딥러닝 기술의 발달로 NLP/NLU의 경계가 애매해지고 있습니다.

전통적인 NLP영역쪽도 딥러닝 기반의 기술을 적용했을 때 더 좋은 성능이 나오고 있거든요.


Tokenizing(Parsing)
한 덩이로 되어있는 문장을 인공신경망에 인식시키기 위해서 세부 단위로 쪼개는 작업이 필요합니다.

이를 토크나이징 또는 파싱이라고 하며, 이 쪼개진 단위를 토큰(token)이라 부릅니다.

어떻게 쪼개면 좋을지는 언어의 특징과 수행하고자 하는 태스크, 데이터의 특징에 따라 다릅니다.

![image](https://github.com/jihye-kim11/sp/assets/59490892/801a10fe-8d6f-4374-9fb1-54a315ff5093)


워드임베딩(word embedding)
이제 한 덩이의 문장이 토큰들로 쪼개졌습니다.

쪼개진 토큰들은 인공신경망이 계산할 수 있도록 벡터로 바꾸어줘야 하는데요, 토큰을 벡터화하는 것을 워드임베딩이라고 부릅니다.

우리가 읽을 수 있는 토큰(보통 단어 단위)을 다차원의 벡터 공간의 한 점으로 매핑한다, 꽂아 넣는다는 의미에서 워드 임베딩이라는 표현을 씁니다.

토큰을 벡터화하는 워드임베딩 기법에는 여러가지가 있습니다.

원-핫 인코딩(One-hot Encoding)
토큰을 벡터화하는 가장 쉽고 직관적인 방법은 우리가 알고있는 모든 토큰들을 쭈루룩 줄세워 사전을 만들고, 순서대로 번호를 붙이는 작업입니다.

내가 가진 모든 문장, 문서들을 토크나이징한 뒤 토큰들의 중복을 제거한 사전을 만듭니다.
사전의 길이(중복 제외 토큰 수)만큼 벡터를 정의하고, 벡터에서 토큰의 순서에 해당하는 위치만 1, 나머지는 0의 값으로 채워 벡터를 구성합니다.
내가 가진 문장, 문서의 토큰들을 해당 벡터로 교체합니다.

![image](https://github.com/jihye-kim11/sp/assets/59490892/f884e768-539d-4d16-ae04-d5a41352035b)

이를 개선하기 위해, 벡터의 길이도 작으면서 정보도 많이 담긴(dense) 두 가지 방식이 나왔습니다.


CBOW와 SKIPGRAM

![image](https://github.com/jihye-kim11/sp/assets/59490892/56e93dc7-195c-4d01-9933-6958c7966712)


사람은 언어를 이렇게 배웁니다. 

우리는 모든 단어를 사전을 뒤져가며 정확한 의미를 습득하는 게 아닙니다. 

비슷한 문맥에서 비슷한 위치에 등장하는 단어끼리는 유사한 의미를 가진다는 걸 알 수 있으니 '청결'이라는 단어를 만일 몰라도, '깨끗'이 나올만한 위치에 쓰인다면 그 뜻을 대강 알 수 있습니다.

또 '매나니'라는 단어의 사전적 정의를 몰라도 등장하는 문맥을 여럿 보면 대강의 의미를 뽑아낼 수 있죠.



이런 과정을 알고리즘으로 구현한 것이 각각 CBOW와 SKIPGRAM입니다.




다양한 자연어이해 과제들 
텍스트를 벡터로 바꾼 뒤라면 인공신경망을 어떻게 구성하느냐에 따라 다양한 태스크를 수행할 수 있습니다.

대표적인 자연어이해 태스크 몇 가지를 소개해드리겠습니다.

문장/문서 분류(Sentence/Document Classification)
입력받은 텍스트를 지정된 K개의 클래스(또는 카테고리) 중 하나로 분류하는 과제입니다.

사용자 리뷰를 감성분석(긍/부정)하거나, 유저의 발화문을 챗봇이 처리할 수 있는 기능 중 하나로 매핑하는 의도분류 등에 쓰일 수 있습니다.


Sequence-to-Sequence
문장/또는 문서를 입력으로 받아 문장을 출력하는 과제입니다.

한 나라의 언어를 다른 나라로 옮기는 번역과제라든지, 긴 문서를 핵심 문장으로 추리는 요약과제가 이에 해당합니다. 

이외에도 자유 대화 등 다양한 과제에 활용 가능합니다.

질의 응답(Question Answering)
사용자 질문이 들어오면 내가 가진 매뉴얼 내에서 가장 답변이 될 가능성이 높은 영역을 리턴하는 MRC(Machine Reading Comprehension)와,

가장 유사한 과거 질문/답변(FAQ)를 꺼내주는 IR(Information Retrieval) 형태가 있습니다.

주로 상담챗봇 및 콜센터에 자주 활용되는 기술입니다.


##시간 흐름에 따른 데이터(Sequential data) 처리하기
딥러닝 알고리즘의 강점은 비정형 데이터를 규칙 없이도 잘 처리할 수 있다는 점입니다.

지난 시간까지 이미지라든가 텍스트와 같은 비정형 데이터를 인공신경망이 처리하는 방식에 대해 소개시켜드렸습니다.

하지만 아마 그동안 대다수가 접할 기회가 많았던 데이터는 주로 정형 데이터였을거라고 생각합니다.

즉 관계형 데이터베이스 자료나 엑셀, CSV파일 등으로 나타낼 수 있는 정리된 데이터 타입이죠.



정형 데이터를 분석하는 대표적인 과제로 시계열 예측분석이 있습니다. 

순차적인 시계열 데이터를 활용하여 근미래에 어떤 데이터 값이 나타날지를 예측하는 과제입니다.

여기에는 시간 흐름에 따라 변화하는 로그성 데이터를 활용합니다.

예를 들어, 직장인들의 꿈(?)인 주가 예측이라든지, 내일의 기상정보 예측과 같은 일입니다.


Recurrent Neural Network(RNN; 순환 신경망)
이런 형태의 데이터를 잘 다루기 위한 인공신경망 종류가 있습니다.

'순환신경망'이라고 하는 RNN(Recurrent Neural Network)인데요, 아래 그림과 같이 생겼습니다.

![image](https://github.com/jihye-kim11/sp/assets/59490892/59ab63ad-5971-4fcb-8ef2-9a02409038da)


기존의 신경망이 벡터, 또는 매트릭스로 변환된 입력 데이터를 가지고 출력을 한다면

RNN 역시 마찬가지 작업을 하지만 하나 다른 점이 있습니다.

[그림 5]에서 볼 수 있듯이, 과거에 데이터를 처리하여 결과를 출력했던 과정의 일부를 가져와 현 시점에서 데이터를 처리하고 결과를 출력하는 데 도움을 주는데요,

그림상에선 오른쪽으로 향하는 가로 방향의 화살표에 해당합니다. RNN에서는 벡터 형태로 정보(feature)가 넘어가죠.

그래서 2번째 시점에는 해당 시각의 입력 데이터 뿐 아니라 1번째 시점의 누적된 정보를 가지고 예측을 출력합니다.

3번째 시점에는 1,2번째 시점의 누적된 정보가 반영될 것이고, 4번째 시점이 되면 1,2,3번째의 압축된 정보가 도움을 줍니다. 

입력 데이터만으로 예측하는 것보다 과거의 누적된 정보(feature)가 있다면 더 개선된 예측을 할 수 있겠죠?

장점
RNN의 특징에 대해 살펴보았는데요, RNN이 가진 장단점에 대해 정리해보겠습니다.

RNN은 시간 흐름에 따른 과거 정보를 누적할 수 있다
위에서 언급한대로, 다른 인공신경망과 달리 RNN이라는 특수한 형태의 신경망은

입력 데이터뿐 아니라 과거의 처리 내역을 반영하여 더 나은 결정을 할 수 있다는 점이 가장 큰 장점입니다.

RNN은 가변 길이의 데이터를 처리할 수 있다
위 일기예보 예시의 경우 3시각 단위로 예측을 하는데, 이러한 단위 시간마다의 매 시점을 timestep이라고 합니다.

timestep은 시간 단위가 될 수도 있고, 일 단위, 월 단위, 초 단위 등... 순서만 존재한다면 각자 구성하기 나름입니다.

RNN은 과거의 정보를 매 timestep마다 압축하여 다음 timestep으로 넘기므로 데이터의 길이에 무관하게 자유롭게 구성할 수 있습니다.

하루치 데이터로 예측을 할 수도 있고, 일주일치 데이터를 모아서 예측할 수도 있고, 한 달치 데이터를 모아서 예측할 수도 있습니다.

데이터가 아무리 긴 시간이나 짧은 시간에 대해 구성되어있다고 해도 같은 내용을 예측한다면 모델을 별도로 구성할 필요가 없습니다.

RNN은 다양한 구성의 모델을 만들 수 있다
유연한 구조를 가진 RNN은 다양한 구조를 활용하여 신경망을 구성할 수 있습니다.

상황에 따라 RNN은 다양하게 입력 데이터를 처리, 누적하고 결과를 예측할 수 있습니다. 

이 때 입력 데이터의 정보를 누적하는 부분을 인코딩(Encoding), 결과를 출력하는 부분을 디코딩(Decoding)이라고 표현합니다.


단점
연산 속도가 느리다
RNN은 과거의 처리 내역을 현재에 반영해야 하기 때문에, 현 시점의 데이터를 처리하려면 반드시 이전 시점의 데이터가 처리 완료되어야 합니다.

따라서 병렬학습이 어렵고, 순차적으로 데이터를 처리해야 하는 성질로 인해 연산 속도가 다소 느린 편입니다.

많은 경우 딥러닝 모델을 이용하여 데이터를 학습시킬 때 GPU 서버를 활용하곤 하는데요,

그래픽(주로 2차원 매트릭스나 3차원 이상의 텐서)을 다루는 데 특화된 GPU 칩은 병렬 연산에 굉장한 이점을 가진 장비입니다.

하지만 RNN을 처리하는 경우 이러한 병렬처리의 이점을 잘 활용할 수 없는 한계가 있습니다.

학습이 불안정하다
또한 단순 RNN은 학습시키기 매우 어려운 딥러닝 알고리즘 중 하나입니다.

미분 수식 전개가 필요하여 자세히 설명드리지는 않겠습니다만, 다루는 데이터의 timestep이 길면 길수록 문제가 발생할 확률이 높습니다.

timestep이 길어지면 RNN 인공신경망이 반영해야 할 과거의 이력이 많아지게됩니다.

이 과정에서 인공신경망이 학습해야 할 값이 폭발적으로 증가하는 현상이 발생할 수 있습니다. 이를 Gradient Exploding이라 합니다.

또 이와는 반대로, timestep이 길어지면 저 멀리 있는 과거의 이력은 현재의 추론에 거의 영향을 미치지 못하는 문제도 생깁니다.

이를 Gradient Vanishing이라고 합니다.

RNN은 상당히 학습이 불안정하여, 이 두 가지 문제가 자주 발생하곤 합니다.



실질적으로 과거 정보를 잘 활용할 수 있는 모델이 아니다
이론적으로 RNN은 과거의 정보가 누적되며 현재 추론에 도움을 주곤 합니다만, 실질적으로 먼 과거의 정보를 반영하긴 힘듭니다.

RNN은 한 timestep씩 정보를 누적하여 인코딩하는데, 먼 과거의 정보는 여러 번 압축되고 누적되다보니 거의 영향을 미치지 못합니다.

이를 RNN의 장기 종속성/의존성 문제(Long-term dependency)라고 합니다.

성능 보완
RNN에 이러한 단점이 있다 보니, 당연히 이를 해결하는 방안도 등장하였습니다. 

LSTM(Long-short term memory)
저 먼 과거의 정보 중 중요한 것은 기억하고, 불필요한 것은 잊어버리도록 스스로 조절 가능한 RNN 유닛이 있습니다.

매번 동일하게 과거의 정보를 누적하고 압축하는 기본 RNN(naive RNN) 유닛과는 달리, 

정보 흐름을 잘 조절하기 위해 성능을 개선한 특별한 형태의 뉴런이라고 생각하시면 됩니다.

대표적으로 LSTM(Long-short term memory)이라는 유닛이 있습니다.

장/단기 메모리 유닛이라는 뜻인데요, 이 유닛은 아래와 같이 생겼습니다.




