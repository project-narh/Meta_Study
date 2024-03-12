# Unity Shader
## 쉐이더 기초
해당 사이트 정리 ![블로그](https://celestialbody.tistory.com/5)
### 백분률
24bit 컬러의 흰색 -> R 255 G 255 B 255 
반대인 검정 -> R 0 G 0 B 0

다만 각 채널이 5,6,5bit가 되는 16bit라면?
흰색 -> R32 B64 B32

이는 압축포멧에 따라서 달라지며 이를 위해 나온것이 백분률
이를 이용하면 최대값이 달라져도 비율을 통해서 원하는 색을 도출하는 개념

### float
float는 32bit(약 42억)
소수점 아래 6번째까지 가능
코드상 색은 각 채널당 32bit를 이용하여 (R = 32bit) (G = 32bit) (B = 32bit)
백분률로 보면 1 = 100%
즉 float3 (1,1,1)로 볼 수 있다
알파를 표현하고 싶으면 float4(R,G,B,A) 즉 32bit를 한개 더 추가한다.

### 셰이더란?
셰이더는 3D 컴퓨터 그래픽에서 물체의 3차원 위치를 나타내는 x,y,z 좌표, 색, 텍스처, 조명등 다양한 시각적 효과를 계산하여 최종적으로 출력할 픽셀의 위치와 색상을 계싹하는 함

이를 위한 종류
HLSL (High Level Shading Language) - 가장 보편적
GLSL (OpenGL Shading Language) - OpenGL에서 사용
CG (c for Graphics) - 엔비디아, 마소 협력 언어

유니티가 사용하는 방식은 CG (URP 및 언리얼은 HLSL)
다만 각 언어들은 정말 유사하니 걱정은 하지 말자

### 유니티 셰이더
유니티의 경우 정통 CG가 아닌 스크립트로 이뤄져있다.
이를 통한 3가지 방법 존재 
1. Shader Lab - 호환성 짱 다만 가능 범위가 낮음 
2. Surface Shader - 
3. Vertex&Fragment Shader - Surface Shader의 상위 버전 CG를 디테일 하게 다룬다

이떄 Surface Shader는 Shader

