<h1>한터글로벌 코딩테스트 2번 문제</h1>

<h2>1.결과화면</h2>
<img src="https://user-images.githubusercontent.com/70881757/236863927-6ee93d9f-b058-4439-9176-566fb4ada214.png">
<img src="https://user-images.githubusercontent.com/70881757/236864074-e2477d20-9661-473e-bfbf-989a029e56bb.png">


<h2>2.코드 및 설명</h2>
해당 코드의 핵심은 반복문과 재귀함수를 이용하여 특정 조건의 배열이 나올때 까지 함수를 구동하는 것입니다.<br/>
function getCombination 은 화폐단위 배열 coin 과 합계 조건 sum 을 인자로 받고 문제 조건을 충족하는 경우의 수 result.length를 반환합니다.<br/>
재귀함수 combinate는 조합된 배열 tempArr 과 그의 합계 tempArrSum, 그리고 눈금자 값인 index를 받습니다.<br/>
tempArrSum 이 sum 과 같거나 클 경우에 재귀문에서 탈출하는데, sum과 같을 경우에는 tempArr를 result 에 추가합니다.<br/><br/>
<img src="https://user-images.githubusercontent.com/70881757/236871048-d2cdc09b-6ecc-47f8-a7ec-c57ddb0eefa6.png"><br/><br/>
(1)tempArrSum이 sum보다 작을 경우<br/>
combinate(0+1 , 0 , [1]) 의 경우 tempArrSum = 1 로 sum = 10 보다 작습니다. 이 경우 한번 더 combinate를 타면서 코드분위(깊이,depth)는 한단계 더 들어가고
combinate(1+1, 0 , [1,1]) 이 수행됩니다.<br/>
(2)tempArrSum 이 sum과 같거나 클 경우<br/>
combinate(3+1, 0, [1,1,1,1])은 탈출 조건을 만족합니다. 이 경우 result.push(tempArr)로 결과값을 저장하고 return으로 되돌아옵니다.<br/>
여기서 return 으로 인해 코드 분위가 한단계 올라오고 for문이 진행되면서 index가 한단계 전진하고 combinate(3+2, 1, [1,1,1,2])가 실행됩니다.<br/>
클 경우도 결과값 저장을 제외하고 같은 로직을 수행합니다.<br/>
(3)종료<br/>
해당 예시에서 coin.length 는 [1,2,3] = 3이므로 index가 3 이상이 되는 순간 로직이 종료되고 result.length 값이 반환됩니다. <br/>
