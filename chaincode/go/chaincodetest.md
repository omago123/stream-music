

Sales1 조직의 peer0 노드에서 Go 체인코드 설치
 
 peer chaincode install -l golang -n music-cc -v 1.0 -p chaincode/go

Sales1 조직의 peer0 노드에서 체인코드 인스턴스화

 peer chaincode instantiate -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -v 1.0 -c '{"Args":[""]}' -P "OR ('Sales1Org.member')"

Sales1 조직의 peer0 노드에서 체인코드 invoke 호출로 initWallet 기능 처리

 peer chaincode invoke -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"initWallet","Args":[""]}'

![image](https://user-images.githubusercontent.com/73014464/140737619-a05843ac-5a66-4136-bb50-95aa559f3c84.png)

판매자 : Hyper     
구매자 : Ledger

Sales1 조직의 peer0 노드에서 체인코드 invoke 호출로 setMusic 기능 처리

판매자 Hyper가 음원 Ledger를 20원의 토큰으로 등록하는 체인코드 실행

 peer chaincode invoke -o order.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"setMusic","Args":["Fabric", "Hyper", "20", "1Q2W3E4R"]}'
 
 ![image](https://user-images.githubusercontent.com/73014464/140740149-77ef269a-0f67-4ad5-9474-4a826ceb47b6.png)
 
 Sales1 조직의 peer0 노드에서 체인코드 invoke 호출로 purchaseMusic 기능 처리
 
  peer chaincode invoke -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"purchaseMusic","Args":["5T6Y7U8I","MS0"]}'
 
 ![image](https://user-images.githubusercontent.com/73014464/140741733-ee1fb133-f961-4509-a6d1-c920b2729330.png)
 
 Sales1 조직의 peer0 노드에서 체인코드 query 호출로 getWallet 기능 처리
 
  peer chaincode query -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"getWallet","Args":["1Q2W3E4R"]}'
  
  peer chaincode query -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"getWallet","Args":["5T6Y7U8I"]}'

  ![image](https://user-images.githubusercontent.com/73014464/140742212-dc55c1ce-8f15-4a2a-bf44-2350f23d03ec.png)

 
 
 
  


 
 


 
 





