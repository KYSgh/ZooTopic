구독형 실시간 뉴스 제공 플랫폼

 https://kysgh.github.io/ZooTopic/

 https://velog.io/@kys/%ED%81%AC%EB%A1%A4%EB%A7%81%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EB%89%B4%EC%8A%A4-%EA%B5%AC%EB%8F%85-%EC%9B%B9-%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A0%9C%EC%9E%91

 
![image](https://github.com/KYSgh/ZooTopic/assets/162289300/38b8a2db-9eaf-49dd-ae95-3bc39a751dd6)
![image](https://github.com/KYSgh/ZooTopic/assets/162289300/baad61f7-8e37-4cbc-a570-2f4cddafb938)

아키텍쳐 -

![image](https://github.com/KYSgh/ZooTopic/assets/162289300/d7c31527-3e2f-424d-9380-1302e7bc4442)

접속,E-Mail 구독 서비스 (상단)

이용자는 구매한 도메인 (ZooTopic.com) Route53을 통해 Waf와 Cloud Front를 거쳐 Zootopic.com에 접속하게 됩니다. (S3정적 웹 호스팅)
메일 구독 서비스를 이용하게 되면 Congnito와 SQS EventBridge 그리고 람다를 통해 SES 이메일을 저장 / 발송 되게 됩니다.

첫 인증 메일 이후 S3 (구독자 전용 뉴스 웹)에서 주간의 핫토픽을 숏폼 형태로 제작한 링크가 전송되어 숏폼 형태의 뉴스를 만나볼 수 있게 됩니다.

뉴스 크롤링 (우측)

뉴스 사이트에서 Event Bridge를 통해 정해진 시간에 크롤링 Lambda를 통해 S3에 RawData를 가져오게 됩니다. 가져온 데이터는 Ajax로 최신화가 이루어져 (S3) ZooTopic에서 새로운 뉴스들을 확인 가능합니다.

ZooChat(채팅 서비스) (Vue.js) (하단)

ApiGateway(WebSocket)를 통해 사용자의 채팅을 전달한뒤 Lambda로 채팅 송신,수신,채팅방 입장시 ID 부여가 이루어져 실시간 채팅 서비스를 지원합니다.


ZooChat (실시간 채팅 서비스) (Vue.js)


![image](https://github.com/KYSgh/ZooTopic/assets/162289300/f732de18-6821-4590-a8dd-5db6f6e42461)



E-Mail 구독 시스템 (SES의 자격 증명에서 추가된걸 확인 할수 있습니다.)


![image](https://github.com/KYSgh/ZooTopic/assets/162289300/932e943e-e686-4738-8878-e4991f7e80b2)

뉴스 크롤링 (S3)



![image](https://github.com/KYSgh/ZooTopic/assets/162289300/53928f5b-0e81-4cd9-b057-c85fa10c4566)




