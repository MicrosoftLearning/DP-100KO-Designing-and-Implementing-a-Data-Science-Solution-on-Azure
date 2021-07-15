---
lab:
    title: '실험 실행'
---
# 실험 실행

데이터 과학자가 수행하는 작업 중 가장 중요한 요소가 실험입니다. Azure Machine Learning에서 *실험*은 스크립트나 파이프라인을 실행하는 데 사용되며 대개 출력 및 레코드 메트릭을 생성합니다. 이 연습에서는 Azure Machine Learning SDK를 사용하여 Python 코드를 실험으로 실행합니다.

## 시작하기 전 주의 사항

*[Azure Machine Learning 작업 영역 만들기](01-create-a-workspace.md)* 연습을 아직 완료하지 않았으면 해당 연습을 완료하여 Azure Machine Learning 작업 영역과 컴퓨팅 인스턴스를 만들고 이 연습에 필요한 Notebook을 복제합니다.

## Jupyter 열기

Azure Machine Learning Studio의 **Notebooks** 페이지를 통해 Notebook을 실행할 수도 있지만, *Jupyter* 등의 모든 기능을 갖춘 Notebook 개발 환경을 사용하면 생산성을 더욱 높일 수 있는 경우가 많습니다. Azure Machine Learning 컴퓨팅 인스턴스에는 Jupyter가 이미 설치되어 있습니다.

> **팁**: Jupyter Notebook은 데이터 과학 작업에 흔히 사용되는 오픈 소스 도구입니다. Jupyter Notebook을 사용해 본 적이 없다면 [설명서](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html)에서 사용법을 참조할 수 있습니다.

1. [Azure Machine Learning Studio](https://ml.azure.com)에서 작업 영역의 **컴퓨팅** 페이지를 표시하고 **컴퓨팅 인스턴스** 탭에서 컴퓨팅 인스턴스가 아직 실행되고 있지 않으면 인스턴스를 시작합니다.
2. 컴퓨팅 인스턴스가 실행되고 있으면 **Jupyter** 링크를 클릭하여 새 브라우저 탭에서 Jupyter 홈 페이지를 엽니다. *JupyterLab*이 아닌 *Jupyter* 홈 페이지를 열어야 합니다.

## Azure Machine Learning SDK가 설치되어 있는지 확인

Azure Machine Learning SDK는 컴퓨팅 인스턴스에 기본적으로 설치되어 있습니다. 설치를 확인하려면 다음 단계를 수행합니다.

1. Jupyter Notebook 환경에서 새 **터미널**을 만듭니다. 그러면 명령 셸이 포함된 새 탭이 열립니다.
2. 다음 명령을 입력하여 Azure ML SDK가 설치되었는지 확인합니다.

    ```bash
    pip show azureml-sdk
    ```

    설치된 SDK 패키지 버전을 확인합니다.

3. Azure Machine Learning 사용 시에 필요한 가장 중요한 라이브러리는 **azureml-sdk** SDK 패키지에서 제공됩니다. 그러나 몇 가지 추가 패키지에서도 기본 SDK 패키지에 포함되어 있지 않은 기타 유용한 라이브러리를 제공합니다. 다음 명령을 사용하여 **azureml-widgets** 패키지도 설치되어 있는지 확인합니다. 이 패키지에는 Azure Machine Learning 정보를 Notebook에 표시하는 데 필요한 라이브러리가 포함되어 있습니다.

    ```bash
    pip show azureml-widgets
    ```

4. **터미널** 탭을 닫고 Jupyter 홈 페이지가 표시된 탭으로 돌아옵니다.

> **추가 정보**: Azure ML SDK 및 선택적 구성 요소 설치에 대한 자세한 내용은 [Azure ML SDK 설명서](https://docs.microsoft.com/python/api/overview/azure/ml/install?view=azure-ml-py)를 참조하세요.

## Notebook에서 실험 실행

Azure Machine Learning의 실험은 일종의 *제어* 레이어(대개 스크립트나 프로그램)에서 시작해야 합니다. 이 연습에서는 Notebook을 사용하여 실험을 제어합니다.

1. Jupyter 홈 페이지에서 Notebook 리포지토리를 복제한 **/users/*your-user-name*/mslearn-dp100** 폴더로 이동하여 **Run Experiments** Notebook을 엽니다.
2. 그런 다음 각 코드 셀을 차례로 실행하여 Notebook의 메모를 읽습니다.
3. Notebook에서 코드 실행이 완료되면 **파일** 메뉴에서 **닫기 및 중지**를 클릭하여 Notebook을 닫고 Python 커널을 종료합니다. 그런 후에 모든 Jupyter 브라우저 탭을 닫습니다.

## 정리

Azure Machine Learning에서 이 랩을 위한 작업이 완료되었으면 Azure Machine Learning의 **컴퓨팅** 페이지 **컴퓨팅 인스턴스** 탭에서 컴퓨팅 인스턴스를 선택한 다음 **중지**를 클릭하여 종료합니다. 완료되지 않았다면 다음 랩을 위해 실행 상태로 둡니다.

> **참고**: 컴퓨팅 인스턴스를 중지하면 컴퓨팅 리소스에 대한 요금이 청구되지 않습니다. 그러나 Azure Machine Learning 작업 영역이 구독에 남아 있으므로 데이터 저장에 대해 소액의 요금이 청구될 수 있습니다. Azure Machine Learning 탐색을 완료한 경우 Azure Machine Learning 작업 영역 및 관련 리소스를 삭제할 수 있습니다. 그러나 이 시리즈의 다른 랩을 완료할 계획인 경우, 먼저 *[Azure Machine Learning 작업 영역 만들기](01-create-a-workspace.md)* 연습을 반복하여 작업 영역을 만들고 환경을 준비해야 하므로 신중히 생각한 후 삭제하는 것이 좋습니다.
