def додати(x, y):
    return x + y
def відняти(x, y):
    return x - y
def помножити(x, y):
    return x * y
def поділити(x, y):
    if y == 0:
        return "Помилка! Ділення на нуль неможливе."
    return x / y

def звести_в_степінь(x, y):
    
    return x ** y

def знайти_корінь(x):
  
    if x < 0:
        return "Помилка! Невід'ємне число."
    return x ** 0.5

def відсоток(x, y):
   
    return (x / 100) * y

def основні_операції():
    
    print("\nОберіть операцію:")
    print("1. Додати")
    print("2. Відняти")
    print("3. Помножити")
    print("4. Поділити")
    print("5. Звести в степінь")
    print("6. Знайти квадратний корінь")
    print("7. Знайти відсоток")
    print("8. Вийти")

def запустити_калькулятор():
    
    while True:
        основні_операції()
        вибір = input("Введіть номер операції: ")

        if вибір in ('1', '2', '3', '4', '5', '7'):
            try:
                num1 = float(input("Введіть перше число: "))
                num2 = float(input("Введіть друге число: "))
            except ValueError:
                print("Неправильне введення. Будь ласка, введіть числа.")
                continue

            if вибір == '1':
                print(num1, "+", num2, "=", додати(num1, num2))
            elif вибір == '2':
                print(num1, "-", num2, "=", відняти(num1, num2))
            elif вибір == '3':
                print(num1, "*", num2, "=", помножити(num1, num2))
            elif вибір == '4':
                print(num1, "/", num2, "=", поділити(num1, num2))
            elif вибір == '5':
                print(num1, "^", num2, "=", звести_в_степінь(num1, num2))
            elif вибір == '7':
                print(f"{num1}% від {num2} =", відсоток(num1, num2))

        elif вибір == '6':
            try:
                num = float(input("Введіть число для знаходження квадратного кореня: "))
            except ValueError:
                print("Неправильне введення. Будь ласка, введіть число.")
                continue
            результат = знайти_корінь(num)
            print(f"Квадратний корінь з {num} =", результат)

        elif вибір == '8':
            print("Дякую за використання супер класного калькулятора!")
            break

        else:
            print("Неправильний вибір. Будь ласка, спробуйте ще раз.")

if __name__ == "__main__":
    запустити_калькулятор()
