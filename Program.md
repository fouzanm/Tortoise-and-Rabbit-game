import random

list=[]
for i in range(4):
    digit=random.randint(0,9)
    list.append(digit)
random_num="".join(str(i)for i in list)


def game(random_num):
    while True:
        num=input("Enter your guess")
        print("System generated digit:",random_num)
        print("Expected Output:")
        if num.isdigit()==True and len(num)==4:
            if num==random_num:
                print("Winner")
                list = []
                for i in range(4):
                    digit = random.randint(0, 9)
                    list.append(digit)
                random_num = "".join(str(i) for i in list)

            else:

                rabbit=0
                for i in range(4):
                    if num[i]==random_num[i]:
                        rabbit+=1
                if rabbit>0:
                    print("You got",rabbit,"Rabbits")

                tortoise=0
                for i in num:
                    if i in random_num:
                        tortoise+=1

                tortoise=tortoise-rabbit
                if tortoise>0:
                    print("You got",tortoise,"Tortoise")
        else:
            print("Invalid input")

        x=input("Do you want to continue?(Y/N)")
        if x.upper()=="Y":
            continue
        else:
            break


game(random_num)


