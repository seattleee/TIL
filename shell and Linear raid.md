QUIZ1. 다음 명령어의 실행 결과가 나머지와 다른 것은?

root@server:/bin# ls

root@server:/bin# ls .

root@server:/bin# ls ./

root@server:/bin# ls /

root@server:/bin# ls /bin

root@server:/bin# ls /bin/*

root@server:/bin# ls /bin/

답: 4번  (상대 / 절대 경로란? *)



QUIZ2. 특정 디렉터리에서 root 사용자 홈 디렉터리로 이동 방법

root@swarm-manager:~/dira# cd 

root@swarm-manager:~/dira# cd ~

root@swarm-manager:~/dira# cd ..

root@swarm-manager:~/dira# cd /

rootroot@swarm-manager:~/dira# cd $HOME

5가지

QUIZ3. 다음 명령어의 실행 결과는?

root@server:/tmp# touch aaa

root@server:/tmp# touch bbb

root@server:/tmp# touch ccc

root@server:/tmp# mkdir ddd

root@server:/tmp# lsaaabbbcccddd ← 디렉터리root@server:/tmp# mv aaa bbb ccc ddd

aaa

bbb

ccc

ddd ← 디렉터리

root@server:/tmp# mv aaa bbb ccc ddd           aaa,bbb,ccc가 3개 파일을 ddd 디렉터리로 옮김

QUIZ 4

 '>' '>>'  차이 



* 숫자 맞추기

  

~~~shell
#!/bin/bash

#r=$(rand)

r=$(shuf =i 100-200 -n 1)

count=0
while [ $count -lt 10 ]
do
	echo "숫자를 입력하세요"
	read num
	
	if [ $num -eq $r ]
	then
		echo "정답입니다"
		exit 0
	fi

	if [ $num -lt $r ]
	then
		echo "더 큰수를 입력하세요."
	else
		echo "더 작은 수를 입력하세요."
	fi
	count=`expr $count + 1`
done
echo "회수를 초과하여 실패했습니다"
exit 1
~~~





* 구구단



~~~shell

# i * j = x
for (( j = 1 ; j < 10 ; j ++ ))
do
	for (( i = 2 ; i < 10 ; i ++ ))
	do
#		echo $i \* $j = `expr $i \* $j`
		printf "%s X %s = %s \t" $i $j `expr $i \* $j`
	done
	printf "\n"
one
exit 0
~~~