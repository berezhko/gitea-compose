services:
  server:
    image: gitea/gitea:latest
    container_name: gitea
    environment:
      - USER_UID=1026
      - USER_GID=100
      - GITEA__database__DB_TYPE=sqlite3
    restart: unless-stopped
    volumes:
      - ./data:/data
      - ./config:/etc/gitea
      - /etc/localtime:/etc/localtime:ro
    ports:
      - "3003:3000"
      - "2002:22"
