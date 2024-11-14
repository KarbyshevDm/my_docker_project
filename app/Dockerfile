# Используем официальный образ Python
FROM python:3.9

ENV PYTHONBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1
# Устанавливаем рабочую директорию
WORKDIR /app

# Копируем файлы зависимостей и устанавливаем их
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Копируем остальные файлы приложения
COPY . .

RUN python manage.py collectstatic
# Запускаем сервер Django
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
