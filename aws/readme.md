# acm-aws
RECA#1 파이널 프로젝트  
AWS 인프라 환경에 HPA를 구성하는 Manifest.  


## AWS Worker node 
AWS는 Openshift AutoScaling을 통해 최소 4대 최소 12대의 워커노드가 구성될 수 있음.

### 워커노드 각각의 리소스
CPU per node: 2
Mem per node: 8Gib  

### 워커노드의 총 리소스 (8대 기준)
Total CPU: 16
Total Mem: 64Gb  

## HPA
### 전체 사용량 제한
워커 노드 전체 리소스의 절반을 해당 프로젝트에 사용할 것임  
Total CPU limit: 8 (Total CPU / 2)  
Total Mem limit: 32Gi (Total Mem / 2)  

### 파드 당 사용량 제한 (파드 8개)
CPU per pod: 1 (Total CPU limit / 8)  
Mem per pod: 4Gi (Total Mem limit / 8)  

### HPA 적용값
Min Pod: 2
Max Pod: 8
CPU avg: 80
Mem avg: 80
