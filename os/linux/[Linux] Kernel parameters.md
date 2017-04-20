# [Linux] Kernel parameters

##### Kernal parameter 확인
> [root@localhost ~]# sysctl -a

<br />

##### packet queue per network device
> [root@localhost ~]# sysctl net.core.netdev_max_backlog

* network device  =>   queue   =>   kernal
* 각 네트워크 장치별 설정
* kernel이 처리하기 전 데이터를 쌓는 queue의 size
* trade off는 memory 사용량

<br />

##### connection queue 
> [root@localhost ~]# sysctl net.ipv4.tcp_max_syn_backlog
> [root@localhost ~]# sysctl net.core.somaxconn

* tcp_max_syn_backlog
  * SYN_RECEIVED 상태의 connection queue 설정 => listen queue
* somaxconn 
  * accept() 처리를 기다리는 connection queue 설정 => accept queue

<br />

### ref
1. http://meetup.toast.com/posts/54
2. https://brunch.co.kr/@alden/6