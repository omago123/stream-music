

Sales1 조직의 peer0 노드에서 Go 체인코드 설치
# peer chaincode install -l golang -n music-cc -v 1.0 -p chaincode/go

Sales1 조직의 peer0 노드에서 체인코드 인스턴스화
#  peer chaincode instantiate -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -v 1.0 -c '{"Args":[""]}' -P "OR ('Sales1Org.member')"

Sales1 조직의 peer0 노드에서 체인코드 invoke 호출로 initWallet 기능처리
#  peer chaincode invoke -o orderer.acornpub.com:7050 -C channelsales1 -n music-cc -c '{"function":"initWallet","Args":[""]}'

![image](https://user-images.githubusercontent.com/73014464/140737619-a05843ac-5a66-4136-bb50-95aa559f3c84.png)






