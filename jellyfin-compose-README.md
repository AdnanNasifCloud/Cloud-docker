services:
  jellyfin:
    image: jellyfin/jellyfin
    container_name: jellyfin
    ports:
      - 8123:8096
    volumes:
      - /home/adnan/mygithub/Cloud-docker/jellyfin-compose/config:/config
      - /home/adnan/mygithub/Cloud-docker/jellyfin-compose/cache:/cache
      - type: bind
        source: /home/adnan/mygithub/Cloud-docker/jellyfin-compose/media
        target: /media
      - type: bind
        source: /home/adnan/mygithub/Cloud-docker/jellyfin-compose/media2
        target: /media2
        read_only: true
    restart: 'unless-stopped'
