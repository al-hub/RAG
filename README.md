# 2024-04-25 AI  

## RAG  
- Retrieval, Augmented, Generation  
- Grounding : 모르는 거 말하지 말고, 주는 거 읽어 --> 니가 생각하지말고 답만해  
- LLM에게 정보를 주는 것  

## Embedding  

- Embedding 자체는 숫자리스트  
- 위치 표현  
- 1536개 (최근모델 3000개) 로 비슷한 것으로 모음  
- similarity(0~1)를 구할 수 있음 : 단어 or 문장 등을 통채로 넣을 수 있음  
- 예시로 환율을 Embbeding을 만들어서, 뉴스를 가지고와서 찾을 수 있음  

## VectorDB  
- 문서 -> Chunking -> 임베딩계산 -> Vector index에 저장 -> VectorDB  
-                                                    사용자 질문에 사용  
- Client Data -> Data Processing -> Generate embeddings -> Embeddings -> Save embeddings -> VectorDB  
- User -> Query -> GenAI Ap -> VectorDB , GenAI App <- LLM
- chunking (문서가 길때 나누는 것) : 너무크도 문제, 너무 작아도 문제 
- 

## 시스템 만들기  
- FineTunning을 할까(LoRa)? or RAG를 할까?  
- 데이터보호 : On-prem(회사내설치), 기존의 data store를 vector-serchable, GDPR(전세계적으로 돌아가야하는 경우), RAI(윤리적AI, responsibile)

## LLM 사용하여 시스템 구축  
- 쓰지말자 (엄청나게 느리고, 비싸다. 초당 Query를 고민)
- non-deterministic
- LLM Ops : DevOps, MLOps, LLMOps, Evolvin stack
- In-house
- PoC는 빠르지만 실제 개발은 멀구도 험한

## Prompt Engineering
- 결국 meta prompt는 써야한다
- 지시사항, 참고사항, 출력 : 짧게, 간결하게, 확실하게
- 원하는것
- 길어지면 구역지정 : <클레임>000</클레임>, <직원응대>000</직원응대>
- 예시들기 : ZeroShot, TwoShot, FewShot
- 생각의 연결고리 ( 거의 다쓴다 ) : Let's work it out step by step
- Tree of Thought : 세명가지고, 각자 아이디를 내고 두명이 투표내고 고르도록 함
- 수정, 수정, 테스트 : 한번으로 끝나는 경우가 없다.
- 포맷은 마크다운
- deterministic outcome은 코드로
- 조심해야 할 부분 - 프롬프트 주입, 탈옥, 유출

