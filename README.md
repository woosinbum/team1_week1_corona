# week1_corona

## 코로나 흉부 ct 사진을 보고 코로나 양성인지 음성인지 판별하는 작업

간단하게 레즈넷을 이용해서 분석을 했을 때 제공받은 트레인 데이터가 600여개 밖에 되지않아 
트레인 데이터에 과적합이 되는 것을 확인하였습니다. 의료 부분 데이터에서 dcgan을 이용한 
데이터 augmentation을 한다는 자료를 보고 dcgan을 이용해서 트레인 데이터를 늘려보았지만
오히려 학습 능력을 저하시켰습니다. 


## ben.tar , neg.tar 파일은 각각 dcgan을 이용해 만든 양성, 음성 코로나 폐 ct 사진 파일입니다.

## 얻은 인사이트
학습 능력이 저하된 이유를 생각해본 결과 일단 만들어진 이미지 파일이 64 x 64 사이즈의 저해상도 사진이어서
원본데이터의 384 x 384 의 이미지와 크게 차이가 났었고 이것을 다시 모델에 돌리기 위해 128 x 128 사이즈로 resize하는 
과정에서 이미지가 커질 때의 원리를 생각해보면 없는 픽셀들을 보간으로 채우면서 원래 가지고있던 어떤 특성들을 다
망가지게 하게 된 것이 아닌가 생각이 들었다.
