# Check the TPU device on the Google Colab

[Google Colab](https://colab.research.google.com/notebooks/intro.ipynb)에서 [PyTorch MNIST 기본 예제](https://github.com/pytorch/examples/tree/master/mnist)를 Multi-core TPUs, Single-core TPU 및 GPU에 맞게 수정하여 학습 시간에 대한 성능 비교(테스트 데이터에 대한 정확도 비교는 하지 않음.)  
자세한 내용은 [PyTorch를 TPU에서 사용해보기 (1)](https://aithlab.github.io/deep%20learning/tpu1/) 및 [PyTorch를 TPU에서 사용해보기 (2)](https://aithlab.github.io/deep%20learning/tpu2/)를 참고할 수 있다.

성능 비교를 진행하면서 이상한 부분은 `.ipynb`파일이 어디서 생성되었느냐에 따라 성능 차이가 있다는 것이다. 다음의 두 방법에 따라 학습 속도의 차이를 보인다.  

1\. [Colab 메모장](https://cloud.google.com/tpu/docs/colabs)에서 제일 아래에 있는 PyTorch용 예제 3개 중 아무거나 들어가서 이미 작성된 코드를 전부 지우고 내가 실행하고자 하는 코드를 붙여 넣은 파일(아래의 표에서 `예제 파일`로 표시)  
2\. Colab 사이트나 Google Drive에서 만든 ipynb 파일에 내가 실행하고자 하는 코드를 붙여 넣은 파일(아래의 표에서 `Colab 파일`로 표시)

첨부된 `.ipynb` 파일에 `_make_from_example`이 붙은 파일이 1번 방법으로 생성된 파일이고 `_make_from_colab`이 붙은 파일이 2번 방법으로 생성된 파일이다. 해당 파일들을 [Google Drive](https://drive.google.com/) 등에 upload하여 Colab으로 테스트해볼 수 있다.  

|  파일 종류      | Multi TPUs (s) | Single TPU  (s) | GPU (s) |
|  :---:        | :---:          | :---:           | :---:   |
| 예제 파일       |**32.868**      | 81.551          |    54.401 |
| Colab 파일     |158.917         | **127.238**     |131.210   |

\* Colab의 경우 동일한 Hardware accelerator 옵션 내에서 매번 같은 device가 할당 되는 것이 아니기 때문에 위의 성능 비교는 조금씩 차이가 있을 수 있다.


