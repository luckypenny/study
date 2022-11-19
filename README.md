# study
# -refresh-only

main.tf -> terraform apply -> 수정(수작업) -> 작업한 내용을 코드화 하여 동기를 맞추려고 한다면

-> terraform -refresh-only -> State File을 운영상태로 최신화 한다. -> terraform state list로 자원을 확보 하고 -> terraform state show aws_security_group.ssh-access 를 통해서 변경된 코드를 확보 합니다.

그 후에 terraform code에 해당 코드를 삽입합니다.

terraform plan 을 하면 - aws_security_group.ssh-access: Refreshing state... [id=sg-0e5e2ae6e9a842350] - aws_instance.webserver: Refreshing state... [id=i-083aa408472e649b6] - No changes. Your infrastructure matches the configuration.

 

# -replace

1. 테라폼으로 엔진엑스가 1.6이 설치된 인스턴스를 구성 했다.

2. 누군가 1.7로 업데이트 했다.

3. 테라폼 apply를 하면 1.6이 설치된 인스턴스가 유지 됨을 기대 한다. 하지만 1.7이 설치 되어 있다.

4. 이런 경우 테라폼으로 해당 인스턴스를 교체 하려고 하는 경우에 사용된다.
