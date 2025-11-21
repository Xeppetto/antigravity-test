# Clustering (군집화)

## 1. 개요 (Overview)
Clustering(군집화)은 정답(Label)이 없는 데이터에서 유사한 특성을 가진 데이터끼리 그룹으로 묶는 [비지도 학습(Unsupervised Learning)](./MLBasic.md) 기법입니다. 고객 세분화, 이상 탐지 등에 사용됩니다.

## 2. 주요 알고리즘 (Key Algorithms)

### 2.1. K-Means Clustering
데이터를 K개의 그룹으로 묶습니다.
1.  K개의 중심점(Centroid)을 임의로 잡습니다.
2.  각 데이터를 가장 가까운 중심점에 할당합니다.
3.  할당된 데이터들의 평균으로 중심점을 이동시킵니다.
4.  중심점이 변하지 않을 때까지 반복합니다.
- 장점: 빠르고 단순함.
- 단점: K값을 미리 정해야 하고, 원형이 아닌 군집은 잘 찾지 못합니다.

### 2.2. DBSCAN (Density-Based Spatial Clustering of Applications with Noise)
밀도가 높은 영역을 군집으로 묶습니다.
- 장점: 군집의 개수를 미리 정할 필요가 없고, 기하학적인 모양의 군집도 잘 찾으며, 노이즈(이상치)를 걸러낼 수 있습니다.

### 2.3. Hierarchical Clustering (계층적 군집화)
데이터 간의 거리를 기반으로 계층적인 트리 구조(Dendrogram)를 만듭니다.

## 3. 평가 지표
정답이 없기 때문에 평가가 어렵지만, **Silhouette Score** (군집 내 거리는 가깝고 군집 간 거리는 먼 정도) 등을 사용합니다.
