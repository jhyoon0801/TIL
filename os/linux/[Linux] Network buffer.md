
# [Linux] Network buffer 

### Network buffer size 확인
##### kernal parameter 전체 조회
>[root@localhost ~]# sysctl -a 

<br />
##### 모든 종류의 소켓
> [root@localhost ~]# sysctl net.core.rmem_default
> [root@localhost ~]# sysctl net.core.wmem_default
> [root@localhost ~]# sysctl net.core.rmem_max
> [root@localhost ~]# sysctl net.core.wmem_max 

* net.core 접두사는 **모든 종류**의 소켓에 기본적으로 설정되는 버퍼 크기
<br />



##### tcp network buffer
> [root@localhost ~]# sysctl net.ipv4.tcp_rmem
> [root@localhost ~]# sysctl net.ipv4.tcp_wmem
> [root@localhost ~]# sysctl net.ipv4.tcp_mem

* net.ipv4 접두사는 TCP 소켓에 적용되는 파라미터이며, net.core 접두사에 적용된 파라미터 값을 덮어쓴다.
* tcp_mem
 * tcp 전체에서 사용할 수 있는 메모리 크기
 * min / pressure / max
 * TCP memory pressure state : 전체 tcp 소켓  메모리가 pressure 값을 초과하면, 이후 생성되는 소켓은 min 값의 메모리 버퍼 크기를 가진다.

<br />

##### udp network buffer
> [root@localhost ~]# sysctl net.core.rmem_default
   [root@localhost ~]# sysctl net.core.rmem_max


ref
1. https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Performance_Tuning_Guide/s-network-dont-adjust-defaults.html
2. http://zetawiki.com/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4_%EC%86%8C%EC%BC%93_%EB%A9%94%EB%AA%A8%EB%A6%AC_%ED%81%AC%EA%B8%B0_%EB%B3%80%EA%B2%BD
3. http://zetawiki.com/wiki/UDP_%EC%88%98%EC%8B%A0_%EB%B2%84%ED%8D%BC_%ED%81%AC%EA%B8%B0
4. http://zetawiki.com/wiki/%EB%A6%AC%EB%88%85%EC%8A%A4_txqueuelen_%ED%99%95%EC%9D%B8
5. http://meetup.toast.com/posts/53
6. https://groups.google.com/forum/#!topic/comp.os.linux.networking/Kzy86QcJ6RM