# rede-corporativa-com-datacenters

# Projeto de Rede Corporativa Simulada - Cisco Packet Tracer

## Visão Geral
Simulação de uma infraestrutura de rede empresarial com múltiplas 
sub-redes, servidores de serviço (DHCP, DNS, WEB, FTP) e distribuição 
hierárquica via switches e roteadores.

## Topologia
- 4 roteadores (Cisco 2911) interligando 4 sub-redes distintas
- Servidores: DHCP, DNS, WEB, FTP
- [X] switches distribuindo acesso para PCs, laptops e impressoras
- Endereçamento IP com VLSM (redes /24 para LAN, /30 para links WAN)

## Tecnologias e Protocolos
- Roteamento dinâmico com RIPv2
- DHCP centralizado com IP Helper-Address (DHCP Relay)
- Sub-redes calculadas com VLSM

## Desafios técnicos e soluções
DHCP não distribuindo entre sub-redes → implementação de IP Helper-Address, já que broadcast DHCP não atravessa roteadores
Conflito de endereçamento nos links entre roteadores → redesenho usando VLSM com blocos /30 dedicados para os links ponto-a-ponto
RIP não convergindo entre roteadores não-adjacentes → identificação de que o simulador estava em modo Simulation (tempo pausado), e ajuste de versão do RIP (v2) com desativação de auto-summary para suportar VLSM

## Diagrama
<img width="929" height="641" alt="Captura de tela 2026-07-01 230806" src="https://github.com/user-attachments/assets/64bc08b1-f411-4b04-a7db-2ad9233305da" />
