# 🌐 Aplicação Lab - Website Dockerizado

Este projeto faz parte de um laboratório DevOps e consiste em uma aplicação web estática containerizada utilizando Docker e Nginx.

O objetivo deste repositório é demonstrar a criação de uma imagem Docker pronta para ser publicada em um registry (Amazon ECR) e posteriormente executada em uma instância EC2.

---

## 📚 Tecnologias

- HTML5
- CSS3
- JavaScript
- Docker
- Nginx

---

## 📁 Estrutura

```
website/
├── css/
├── js/
└── index.html

Dockerfile
```

---

## 🐳 Dockerfile

A aplicação utiliza uma imagem oficial do Nginx.

```dockerfile
FROM nginx:alpine

COPY website/ /usr/share/nginx/html

EXPOSE 80

CMD ["nginx","-g","daemon off;"]
```

---

## 🚀 Executando Localmente

### Clonar o projeto

```bash
git clone https://github.com/SEU-USUARIO/aplicacao-lab.git

cd aplicacao-lab
```

### Build da imagem

```bash
docker build -t website .
```

### Executar container

```bash
docker run -d \
-p 80:80 \
--name website \
website
```

Abra:

```
http://localhost
```

---

## ☁️ Deploy na AWS

A imagem foi projetada para ser enviada ao Amazon ECR e executada em uma instância EC2 provisionada via Terraform.

Fluxo utilizado:

```
Desenvolvimento
        │
        ▼
 Docker Build
        │
        ▼
 Amazon ECR
        │
        ▼
 Amazon EC2
        │
        ▼
     Usuário
```

---

## 🎯 Objetivos do projeto

- Containerizar uma aplicação
- Utilizar imagem oficial do Nginx
- Padronizar ambiente de execução
- Preparar a aplicação para deploy automatizado
- Integrar com infraestrutura provisionada via Terraform

---

## 📷 Demonstração

assets/example.jpg

---

## 👨‍💻 Autor

Bruno Abreu

LinkedIn: https://linkedin.com/in/bruno--abreu

GitHub: https://github.com/BrunoAbr

Laboratório pensado por: Maria Lazara
