# acm-vsphere
RECA#1 파이널 프로젝트  
vSphere 인프라 환경에 HPA를 구성하는 Manifest.  


## vSphere Worker node 
### 워크노드 각각의 리소스
CPU per node: 4  
Mem per node: 16Gb  

### 워커노드의 총 리소스
Total CPU: 12  
Total Mem: 48Gb  

## HPA
### 전체 사용량 제한
워커 노드 전체 리소스의 절반을 해당 프로젝트에 사용할 것임  
Total CPU limit: 6 (Total CPU / 2)  
Total Mem limit: 24Gi (Total Mem / 2)  

### 파드 당 사용량 제한 (파드 6개)
CPU per pod: 1 (Total CPU limit / 6)  
Mem per pod: 4Gi (Total Mem limit / 6)  

### HPA 적용값
Min Pod: 2
Max Pod: 6
Min CPU: 2 (CPU per pod * Min Pod)
Max CPU: 6 (CPU per pod * Max Pod)
Min Mem: 8Gi (Mem per pod * Min Pod)
Max Mem: 24Gi (Mem per pod * Max Pod)
