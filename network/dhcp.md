# DHCP

IP를 동적으로 할당하는 데 사용되는 프로토콜이 바로 DHCP (Dynamic Host Configuration Protocol) 입니다. DHCP를 사용하면 사용자가 직접 입력해야 하는 IP 주소, 서브넷 마스크, 게이트웨이, DNS 정보를 자동으로 할당받아 사용할 수 있습니다. 

## DHCP 동작 방식

### 호스트가 DHCP 서버로 IP를 할당받는 과정

1. DHCP Discover
   - DHCP 클라이언트는 DHCP 서버를 찾기 위해 DHCP Discover 메시지를 브로드캐스트로 전송합니다.
2. DHCP Offer
   - DHCP Discover를 수신한 DHCP 서버는 클라이언트에 할당할 IP 주소와 서브넷, 게이트웨이, DNS 정보, Lease Time 등의 정보를 포함한 DHCP 메시지를 클라이언트로 전송합니다.
3. DHCP Request
   - DHCP 서버로부터 제안받은 IP 주소와 DHCP 서버 정보를 포함한 DHCP 요청 메시지를 브로드캐스트로 전송합니다.
4. DHCP Acknowledgement
   - DHCP 클라이언트로부터 IP 주소를 사용하겠다는 요청을 받으면 DHCP 서버에 해당 IP를 어떤 클라이언트가 언제부터 사용하기 시작했는지 정보를 기록하고 DHCP Request 메시지를 정상적으로 수신했다는 응답을 전송합니다.

### DHCP 갱신 절차

DHCP에서 IP를 할당받은 후 임대 시간의 50%가 지나면 DHCP 갱신 과정을 수행합니다. DHCP 클라이언트는 처음 수행한 임대 과정과 달리 DHCP 서버 정보와 이미 사용 중인 IP 정보가 있어 DHCP Discover와 DHCP Offer 과정을 생략하고 DHCP Request를 DHCP로 곧바로 전송하고 DHCP 서버에서는 DHCP ACK를 보내면서 갱신 과정을 진행합니다. 이처럼 갱신 과정은 초기 임대 과정과 비교하면 절차가 짧을 뿐만 아니라 브로드캐스트가 아닌 유니캐스트로 진행되므로 불필요한 브로드캐스트가 발생하지 않게 됩니다.

만약 임대 시간이 50%가 지난 시점에서 갱신이 실패하면 남은 시간의 50%가 지난 시점, 즉 초기 임대 시간의 75%가 지난 시점에서 갱신을 다시 시도하게 됩니다. 만약 이때도 갱신을 실패하면 추가 갱신 없이 임대 시간이 모두 지난 후에 IP를 반납하고 다시 처음부터 IP를 할당받게 됩니다.

&nbsp;

Excerpt From <IT 엔지니어를 위한 네트워크 입문> by 고재성, 이상훈
