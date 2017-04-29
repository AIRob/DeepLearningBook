
For english versio, please click[here](root/README.md)

# ׼������
Ҫִ�б��̵̳Ĵ��룬����������Ҫ��װ���������������⣺
 - ��װVisual Studio 2013 or 2015.
 - ��װAnaconda2. ����Theano�İ�װ��Ҫ�����������⣬Ϊ�˱��ⰲװ������ʧ�ܣ���ǿ�ҽ��鰲װAnaconda��AnacondaΪ���ǹ�����һ��ǿ��python�����������������������沿�𹤳���Ŀ�����������Ѿ���װ�˳���700�����õİ��������˾��󲿷ֵĿ�����Ҫ�����߿����ڹٷ����ذ�װ��https://www.continuum.io/downloads/. ע�⣬Anaconda2�������python2��Anaconda3�������python3�����̳���ʹ�õ���Anaconda2��Ҳ����python2��д������㰲װ����python3����������ĳЩ�޸�ĳЩ�����﷨��
 - ��װmingw��libpython. ������Ѿ���װ��Anaconda2, ��ôֻ��Ҫ�������д���������"pip install mingw"��"pip install libpython"���Ϳ��Էֱ�װ�ⰴ���⡣
 ```javascript
 pip install mingw
 ``` 
 ```javascript
 pip install libpython
 ``` 
 - CUDA 8.0 (��ѡ). ������뽫�������GPU�Ͻ��м��٣���ô����Ҫȷ������һ��NVIDIA��GPU�Կ�������֧��CUDA, Ȼ����NVIDIA�Ĺٷ���վ�����ذ�װCUDA toolkit: https://developer.nvidia.com/cuda-downloads  
 - ��װTheano 0.8���߸��ߵİ汾. �������д���������"pip install theano"��ϵͳ�ͻ�Ϊ���Զ���װ���µ�Theano��
 ```javascript
 pip install theano
 ```

���㰴������Ĳ���ִ����Ϻ��������д���������"python"����python�Ĺ���������Ȼ������"import theano"�����û�б������ҵõ��������Ϣ(������ϵͳ������ͬ����ʾ����Ϣ�᲻һ��)����ô����ϲ�㣬���Ѿ��ɹ���װTheano�Ŀ������������Ա�д�����ˡ�

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/theano1.png)
 
# Ӳ��
| ����     | ��Ϣ|
|:--------:|:---------:|
|CPU|intel Core i7-6700K|
|RAM|16GB������|
|GPU|Nvidia GeForce GTX 1080|

# Ӧ��һ: cifar10ͼ�����
### 1.1 ��������:
>  CIFAR-10ͼ�����. CIFAR-10��6���Ŵ�СΪ32*32*3���ɵ�ͼ�񼯣��ɶ��׶��ѧ��Alex Krizhevsky, Vinod Nair��Geoffrey Hinton�ռ���ά�������ݼ������ص�ַΪ��(https://www.cs.toronto.edu/~kriz/cifar.html)

�ڱ�Ӧ���У��ҳ����������4�ֲ�ͬ������ģ�������з��ࣺ
 - softmax�ع�: û�����ز�����磬����300�εĵ���֮�󣬵õ��ķ��������ԼΪ0.6 
 - ����֪��: ��2�����ز�, ÿһ�����ز�ֱ���1000���ڵ�. ����300�εĵ���֮�󣬵õ��ķ��������ԼΪ0.5��
 - ջʽ�����Ա�����: �������׶Σ���һ�׶���Ԥѵ����������ʼ�������Ȩ�ز�����2�� ΢��������ͨ��������ѵ������һ��������300�εĵ���֮�󣬵õ��ķ��������ԼΪ0.45�� 
 - ���������: 3������㣬3���ػ��㣬�������ػ����ԣ�����300�εĵ���֮�󣬵õ��ķ��������ԼΪ0.25��

**ע�⣺��û�ж�����ģ�ͽ��н�һ�����Ż������߿��������޸ĳ������������޸�����Ľṹ����ø��õ����ܣ����磬�������dropout��ֹ����ϣ�CNNʹ�ø���ľ�����**

### 1.2 ���ܷ���:
�������д���������cd�������"cifar10 classification"�ļ���, �ֱ�ִ��"softmax.py", "mlp.py", "cnn.py", "sda.py"����������в�ͬ��ģ�͡�

��ͼչʾ�˲�ͬ��ģ�ͣ����ŵ������������ӣ���Ӧ�ķ�������ʵ��������ƶԱ�:

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/cifar10.png)


# Ӧ�ö�: ���Ի��Ƽ�
### 2.1 ��������:
> �����Ӧ���֣����ǲ��û���RBM��Эͬ�����㷨�����и��Ի��Ƽ�������RBM��Эͬ���ˣ���������Hinton������2006�����������Ҳ�ǵ����Netflix�����б�����õĵ�ģ��֮һ������ϸ��ʵ�֣����߿��Բο��鱾��11�µĽ��⣬���߲�������: http://www.utstat.toronto.edu/~rsalakhu/papers/rbmcf.pdf

Ҫ���б��ڴ��룬����Ҫ��������Ĵ�����ִ�У�

����һ: ����"Recommendation"�ļ���, ����"data_preprocess.py"�ű�, �㽫�õ�һ���µ��ļ�"data.pkl"�����ļ�Ϊ���װ��ģ������Ҫ���������ݽṹ�������ݽṹ������������ݣ�
 - min_user_id
 - max_user_id
 - min_movie_id
 - max_movie_id
 - train_set
 
Step 2: ����"rbm.py"�ű���ѵ��ģ��

### 2.2 ���ܷ���:
�ڱ�Ӧ���У���ʹ��������5����ͬ��ѵ�����ԣ�����������cd�Ĳ�����ͨ����˵cd�Ĳ���Խ��Gibbs������׼ȷ�Ⱦ�Խ�ߣ�������ʱ��Ҳ����������һ�ͷ��������Կ������ֲ�ࣻʹ��persistent��Ҳ����ÿһ�ε�gibbs������㲻�����¿�ʼ����������һ�ε���β��Ϊ����Gibbs�����Ŀ�ʼ����������Ҳ�����ͨ�ĶԱ�ɢ���㷨Ч��Ҫ�ã�����һ�����������Ӧ����ѧϰ�ʺ�Gibbs���������Ĳ��ԣ����Ƿ��֣���̬������������Ч��Ҫ�����ھ�̬�̶��ĳ�������

 - learning rate=0.01, cd_k=3, after 20 epochs, get error rate 25%
 - learning rate=0.01, cd_k=10, after 20 epochs, get error rate 23%
 - learning rate=0.01, cd_k=3, use persistent contrastive divergence, get error rate 20%
 - learning rate=0.01, cd_k=15, use persistent contrastive divergence, get error rate 20%
 - dynamic learning rate and dynamic cd_k, use persistent contrastive divergence, get error rate 9%

��ͼ�ǲ�ͬ�Ĳ��Զ�Ӧ�Ĵ���������ͼ��
![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/rbm.png)


# Ӧ����: ����ģ��
### 3.1 ��������:
> ��Ӧ����ʹ��LSTMģ������������ģ�ͣ����ǲ��õ����ݼ�ժȡ��Google BigQuery��reddit comments

 - small dataset: ����60000����������.
 - large dataset: ����400000����������.

ͳ������ģ�ͱ�������һ�����ʷֲ�ģ�ͣ�ͨ������ģ�ͣ����ǿ��Եõ�����һ�����ӵĸ��ʴ�С����������ѧ��ʽ������ʽ���ر�ʾΪ��

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/language_model2.png)

### 3.2 ����ṹ:

����LSTM������ģ������ṹ����ͼ��ʾ����ÿһ�����ӵ�ÿһ��������Ϊÿһ��ʱ�䲽�����룬��Ԥ����һʱ�䲽�Ľ��������ʣ�����ϸ��ϸ�ڣ����߿��Բ����鱾�ĵ�ʮ���£�

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/language_model3.png)

### 3.3 ���ܷ���:
�������д���������cd�������"Language model"�ļ��У�����"lstm.py"�ű������õ������ÿһ�����������

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/lstm_output.png)

����100�εĵ���ѵ������ʧ������������������ͼ��ʾ��
**ע�⣺��������������Ƚϴ���ˣ�ǿ�ҽ��齫���������GPU������**

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/language_model.png)


# Ӧ����: ��з���
### 4.1 ��������: 
> �ڱ������У���ʹ���˾����������ʵ���ı����࣬������ʹ�õ����ݼ���Դ��imdb���������ݼ������ݼ������ص�ַΪ��http://ai.stanford.edu/~amaas/data/sentiment/. �����������һ���������ݣ�ģ���ܹ�Ԥ����������������ۻ��Ǹ������۵ĸ���

### 4.2 ׼������:

 - ��Ӧ����Ҫ���ʽ��д���������Ϊ�ˣ����ǿ��Խ���һЩ���е��Ѿ�����õĴ��������ߣ��ڱ�Ӧ���У�����ʹ����Google������Google New���������ߣ��ô���������ͨ��ѵ������1000�ڸ����ʵ����Ͽ�õ��������˳���300������ʵĴ�������ÿһ����������300ά�����������ߵ����ص�ַΪ��https://code.google.com/p/word2vec/��
 - ��װNLTK���߰�����Ҫ�����ڶ��ı��ִʡ�

����һ: ��ѹimdb���ݼ��ļ��������ļ���(aclImdb_v1.tar.gz).
 
�����: ����"data_preprocess.py"�ű�, �ű��������ݼ����н��������õ�����ļ����ṹ��,�Թ�ѵ��ʹ��:

 - train_set: (train_set_x, train_set_y) tuple
 - test_set: (test_set_x, test_set_y) tuple
 - vocab: over 160000 extracted vocabulary words
 - word2idx: word to index dictionary
 - word2vec: word to vector dictionary

������: ����"cnn_classification.py"�ű��������ݽ��з��࣬��ϸ��ʵ��ϸ�ڣ����߿��Բο��鱾�ĵ�ʮ���¡�

### 4.3 ����ṹ:
![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/cnn.png)

### 4.4 ���ܷ���:
��Ӧ�õ�CNNģ�ͣ���Ҫ����AlexNet�ļܹ�����ȫ���Ӳ������Dropout���ԣ��ֱ���4�ֲ�ͬ���Ż����ԣ�Ч������ͼ��ʾ��
**ע�⣺CNNģ�͵��������ǳ�����ˣ�ǿ�ҽ��齫���������GPU������**

![image](https://github.com/innovation-cat/DeepLearningBook/raw/master/raw/performance.png)