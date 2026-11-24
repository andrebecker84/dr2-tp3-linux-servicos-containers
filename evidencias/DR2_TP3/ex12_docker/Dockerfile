# Aplicação mínima: página estática servida pelo httpd do BusyBox (imagem de ~4 MB)
FROM busybox:1.37
LABEL org.opencontainers.image.title="tp3-app" org.opencontainers.image.authors="André Luis Becker"
WORKDIR /www
COPY index.html .
EXPOSE 8080
# -f: fica em primeiro plano (vira o PID 1 do container); -v: log de cada acesso
CMD ["httpd", "-f", "-v", "-p", "8080", "-h", "/www"]
