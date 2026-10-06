# Audivo Mini

PWA estático para transformar links do YouTube em áudio local e reproduzir com HTML5 Audio + Media Session.

## Recursos

- Biblioteca local em IndexedDB.
- Retomada exata da posição.
- Player HTML5 real, sem iframe.
- Controles de tela bloqueada via Media Session.
- Voltar 15s / avançar 30s.
- PWA + Service Worker.
- Download do arquivo para o aparelho.
- Erro de áudio exibido somente quando o elemento realmente entra em estado de erro.

## Download

O adaptador inicial usa o endpoint público documentado pelo projeto Audivo original. Ele recebe um link do YouTube e retorna um link direto de áudio. Essa dependência externa pode mudar ou ficar indisponível; o player foi separado dela para podermos trocar depois por Cloudflare Worker/R2 sem reescrever a biblioteca ou o player.

## Publicação

O projeto pode ser publicado como site estático em GitHub Pages, Cloudflare Pages ou outro host estático. No iPhone, abra no Safari e use Compartilhar → Adicionar à Tela de Início.

## Arquitetura

YouTube → adaptador de download → Blob → IndexedDB → HTML5 Audio → Media Session → tela bloqueada.

O próximo teste importante é importar um audiobook real e confirmar download completo, retomada e reprodução com a tela bloqueada no iPhone.
