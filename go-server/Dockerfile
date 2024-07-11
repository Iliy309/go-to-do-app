# Используем официальный образ Go для сборки приложения
FROM golang:1.16-alpine AS builder

# Устанавливаем рабочую директорию внутри контейнера
WORKDIR /app

# Копируем go.mod и go.sum и устанавливаем зависимости
COPY go.mod go.sum ./
RUN go mod download

# Копируем остальные файлы и собираем приложение
COPY . .
RUN go build -o main .

# Используем минимальный образ для запуска приложения
FROM alpine:latest
WORKDIR /root/
COPY --from=builder /app/main .
COPY .env .
EXPOSE 8080

# Запускаем приложение
CMD ["./main"]
