## **지출 카테고리별 캐시백 기능을 추가한 가계부 프로그램**

<img width="402" height="710" alt="image" src="https://github.com/user-attachments/assets/0d01594e-87de-4040-a292-2ed631692780" />

```
def add_expense(self, category, description, amount):
        today = datetime.date.today().isoformat()
        expense = Expense(today, category, description, amount)
        self.expenses.append(expense)

        cashback_rates = {
            "식비": 0.02,
            "교통": 0.05,
            "문화생활": 0.03,
            "취미": 0.01,
            "자기개발": 0.02
        }
        rate = cashback_rates.get(category, 0.01)
        cashback = int(amount * rate)

        self.cashback_balance += cashback
        print(f"지출이 추가되었습니다. (캐시백 {cashback}원 적립)\n")

def show_cashback(self):
        print(f"현재 캐시백 총액: {self.cashback_balance}원\n")

```

**핵심 기능**

1. Budget 클래스의 add_expense 함수 수정
- 카테고리를 key 값에, 캐시백 적립 비율을 value 값에 할당한 cashback_rates 딕셔너리를 생성함.
- 위 딕셔너리에서 선언되지 않은 카테고리일 경우, 지출 금액의 0.01만큼 캐시백함.

2. Budget 클래스에 show_cashback 함수 생성
- main 함수에서 호출할 용도의 함수임.
