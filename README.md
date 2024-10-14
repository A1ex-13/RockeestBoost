<div id="header" align="center">
  <img src="https://github.com/A1ex-13/RocketBoost/blob/main/rb.png" width="200"/>
</div>  

# RockeetBoost  

попробуй калькулятор [прямо в браузере](https://a1ex-13.github.io/RockeetBoost/RockeetBoost.html)

# 🚀 - рассчитай тягу ракетного двигателя на основе введенных значений  

```python
import math

def calculate_thrust(m_dot, T_c, gamma, M, P_e, P_c, A_e, P_a):
    """
    Расчет тяги ракетного двигателя.
    """
    # Универсальная газовая постоянная (Дж/моль·К)
    R = 8.314

    # Расчет эффективной скорости истечения v_e
    v_e = math.sqrt(
        (2 * gamma * R * T_c) / ((gamma - 1) * M) * (1 - (P_e / P_c) ** ((gamma - 1) / gamma))
    )

    # Расчет тяги
    thrust = m_dot * v_e + (P_e - P_a) * A_e

    # Вывод результата
    print(f"Тяга двигателя: {thrust:.2f} Н")

# Ввод данных от пользователя
m_dot = float(input('Введите массовый расход топлива (кг/с): '))
T_c = float(input('Введите температуру в камере сгорания (К): '))
gamma = float(input('Введите показатель адиабаты: '))
M = float(input('Введите молекулярную массу продуктов сгорания (кг/моль): '))
P_e = float(input('Введите давление на выходе из сопла (Па): '))
P_c = float(input('Введите давление в камере сгорания (Па): '))
A_e = float(input('Введите площадь выходного сечения сопла (м^2): '))
P_a = float(input('Введите атмосферное давление (Па): '))

# Вызов функции с введенными значениями
calculate_thrust(m_dot, T_c, gamma, M, P_e, P_c, A_e, P_a)
```
