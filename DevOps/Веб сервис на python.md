# Обновление данных через веб-сервис
Простейший веб-сервис на Python.

### 🚀 Простой веб-сервис на Flask

**1. Установите Flask:**
```bash
pip install flask
```

**2. Создайте файл `app.py`:**
```python
from flask import Flask, jsonify
import subprocess
import os

app = Flask(__name__)

# Простой ключ для базовой защиты (можно передавать как параметр в URL)
SECRET_TOKEN = "your_secret_token_here"

@app.route('/trigger-data-refresh')
def trigger_refresh():
    # Проверяем токен для безопасности
    token = request.args.get('token', '')
    if token != SECRET_TOKEN:
        return jsonify({"status": "error", "message": "Invalid token"}), 401
    
    try:
        # Запускаем ваш скрипт
        # Убедитесь, что указали полный путь к скрипту
        result = subprocess.run(
            ["/path/to/your/refresh_script.sh"], 
            capture_output=True, 
            text=True, 
            timeout=300  # таймаут 5 минут
        )
        
        if result.returncode == 0:
            return jsonify({
                "status": "success", 
                "message": "Data refresh started successfully",
                "output": result.stdout
            })
        else:
            return jsonify({
                "status": "error", 
                "message": "Script execution failed",
                "error": result.stderr
            }), 500
            
    except subprocess.TimeoutExpired:
        return jsonify({
            "status": "error", 
            "message": "Script timeout"
        }), 500
    except Exception as e:
        return jsonify({
            "status": "error", 
            "message": str(e)
        }), 500

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000, debug=True)
```

**3. Создайте скрипт обновления `refresh_script.sh`:**
```bash
#!/bin/bash
# Ваши команды для обновления витрины
echo "$(date): Starting data refresh"
# Например, запуск SQL-запроса, Python-скрипта и т.д.
python /path/to/your/actual_refresh_script.py
echo "$(date): Data refresh completed"
```

**4. Дайте права на выполнение:**
```bash
chmod +x refresh_script.sh
```

**5. Запустите сервис:**
```bash
python app.py
```

### 🔧 Настройка для продакшена

Для постоянной работы сервиса лучше использовать production-сервер:

```bash
pip install gunicorn
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

Или настройте как systemd-сервис:

**`/etc/systemd/system/data-refresh.service`:**
```ini
[Unit]
Description=Data Refresh Service
After=network.target

[Service]
Type=simple
User=your_user
WorkingDirectory=/path/to/your/script
ExecStart=/usr/local/bin/gunicorn -w 4 -b 0.0.0.0:5000 app:app
Restart=always

[Install]
WantedBy=multi-user.target
```

### 🔒 Безопасность

1. **Измените SECRET_TOKEN** на сложную строку
2. **Настройте firewall** чтобы сервис был доступен только из внутренней сети
3. **Используйте HTTPS** если сервис доступен извне
4. **Ограничьте права** у пользователя, от которого запускается скрипт

### 📱 Использование в Superset

В Custom SQL Superset:
```sql
SELECT 
    ...,
    '<a href="http://your-server:5000/trigger-data-refresh?token=your_secret_token_here" target="_blank" style="padding: 8px 15px; background: #20a0ff; color: white; text-decoration: none; border-radius: 4px;">🔄 Обновить данные</a>' AS refresh_button
FROM your_table
```
