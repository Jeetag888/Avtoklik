import pyautogui
import time
import keyboard  # Для зупинки програми

# Функція для автоклікера з ритмом
def autoclicker_with_rhythm():
    print("Автоклікер запускається через 5 секунд. Натисніть 'q' для зупинки.")
    time.sleep(5)  # Затримка перед початком, щоб ви могли налаштувати курсор
    
    # Темп пісні приблизно 90 BPM = 0.666 секунди на удар (60 / 90)
    base_delay = 0.666  # Базова затримка між кліками
    
    # Ритмічний патерн (приблизний, заснований на структурі пісні)
    rhythm_pattern = [
        base_delay,      # "Ой у лузі"
        base_delay * 0.5, # "червона"
        base_delay,      # "калина"
        base_delay * 1.5, # "похилилася" (довша пауза)
        base_delay,      # "Чогось наша"
        base_delay * 0.5, # "славна"
        base_delay,      # "Україна"
        base_delay * 2    # "зажурилася" (ще довша пауза)
    ]
    
    try:
        while True:
            # Проходимо по ритмічному патерну
            for delay in rhythm_pattern:
                if keyboard.is_pressed('q'):  # Зупинка при натисканні 'q'
                    print("Автоклікер зупинено.")
                    return
                pyautogui.click()  # Симуляція кліку
                print("Клік!")
                time.sleep(delay)  # Затримка відповідно до ритму
    except Exception as e:
        print(f"Помилка: {e}")

# Запуск автоклікера
if __name__ == "__main__":
    autoclicker_with_rhythm()
