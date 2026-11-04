EU CRIEI UM MONSTRO DO SUPORTE - Use com moderação.
Ferramenta de Suporte - Windows 11

Ferramenta em Batch (.BAT) desenvolvida para centralizar rotinas de diagnóstico, manutenção, reparo e suporte técnico no Windows 11.

O projeto foi pensado principalmente para uso por equipes de Help Desk, Service Desk, Field Service e suporte de TI, reunindo comandos nativos do Windows em uma interface simples e organizada.

Objetivo

Reduzir o tempo gasto em tarefas repetitivas de suporte, disponibilizando em um único painel operações para:

diagnóstico do Windows;
correção de arquivos corrompidos;
manutenção do sistema;
diagnóstico de hardware;
drivers;
rede;
DNS;
Windows Update;
Microsoft Teams;
áudio;
teclado;
impressoras;
bateria;
BitLocker;
Microsoft Store;
logs;
políticas;
processos;
serviços;
problemas comuns do Windows 11.
Interface

Ao iniciar a ferramenta, o técnico pode escolher a cor das letras do painel.

O fundo permanece preto para preservar legibilidade e compatibilidade com o Prompt de Comando.

O painel apresenta informações do equipamento, como:

Plain Text
MAQUINA : NOTE-SUPORTE-01
SERIAL : ABC1234
LOGIN : DOMINIO\usuario
LIGADA : 2d 4h 32min

As informações disponíveis podem variar conforme hardware, firmware e permissões do Windows.

Recursos
Sistema e Windows

Rotinas para manutenção e recuperação do sistema operacional:

Reparação com DISM
Verificação com SFC
Verificação de disco com CHKDSK
Limpeza de componentes do Windows
Limpeza segura de arquivos temporários
Otimização do Windows 11
Diagnóstico de inicialização
Análise de serviços
Relatório de falhas recentes
Reparação da Microsoft Store
Diagnóstico de arquivos corrompidos

Exemplos de comandos utilizados:

BAT
DISM /Online /Cleanup-Image /CheckHealth
DISM /Online /Cleanup-Image /ScanHealth
DISM /Online /Cleanup-Image /RestoreHealth
sfc /scannow
chkdsk C: /scan
Rede e Internet

Ferramentas voltadas para problemas como:

computador sem internet;
Wi-Fi conectado sem acesso;
endereço IP incorreto;
problemas de DNS;
Winsock corrompido;
adaptador de rede com falha;
driver de rede;
DHCP;
gateway;
Windows Update sem comunicação;
relógio sem sincronização.

Entre os comandos disponíveis:

BAT
ipconfig /flushdns
ipconfig /release
ipconfig /renew
 
netsh winsock reset
netsh int ip reset
 
pnputil /scan-devices
Hardware e Drivers

Recursos para diagnóstico e manutenção de dispositivos:

diagnóstico de drivers;
dispositivos com erro;
nova detecção de hardware;
backup de drivers;
CPU;
memória RAM;
bateria;
energia;
BitLocker;
teclado;
áudio;
fones;
adaptadores de rede.

A ferramenta utiliza recursos nativos como:

BAT
pnputil /enum-drivers
pnputil /enum-devices /problem
pnputil /scan-devices
driverquery
powercfg
Áudio e Fones

Rotina específica para situações como:

computador sem áudio;
fone conectado mas não reconhecido;
dispositivo de reprodução desapareceu;
serviço de áudio parado;
dispositivo de áudio com problema de driver.

A ferramenta pode reiniciar serviços como:

BAT
Audiosrv
AudioEndpointBuilder

Também executa uma nova detecção dos dispositivos utilizando:

BAT
pnputil /scan-devices
Teclado

Rotina para situações em que:

teclado deixa de responder;
teclado USB não aparece;
teclado interno apresenta problema;
dispositivo HID apresenta falha;
driver deixa de ser carregado.

A ferramenta verifica serviços relacionados a HID e executa novamente a detecção do hardware.

Impressoras

Ferramentas para:

impressora que não imprime;
documentos presos na fila;
Spooler parado;
fila de impressão corrompida.

Inclui reinicialização do:

BAT
spooler

e limpeza da fila de impressão quando solicitado.

Microsoft Teams

Possui rotina destinada à limpeza do cache local do Microsoft Teams.

A ferramenta verifica os caminhos utilizados pelo cliente instalado e encerra o aplicativo antes da limpeza.

Após a limpeza, o primeiro início do Microsoft Teams pode levar mais tempo enquanto os arquivos locais são reconstruídos.

Windows Update

Possui rotina para redefinir componentes relacionados ao Windows Update.

A ferramenta pode reiniciar serviços como:

Plain Text
BITS
Windows Update
Cryptographic Services
Windows Installer

e recriar caches utilizados pelas atualizações.

Informações do equipamento

A ferramenta possui consultas para facilitar o atendimento técnico, incluindo:

nome do computador;
serial;
usuário conectado;
tempo desde a última inicialização;
informações do Windows;
armazenamento;
bateria;
energia;
processos;
drivers;
serviços.

Isso facilita a coleta de informações durante um chamado sem precisar executar vários comandos manualmente.

Catálogo de problemas do Windows 11

Além das ferramentas automáticas, o projeto possui um catálogo para problemas que não devem necessariamente receber uma correção automática.

Entre os cenários contemplados estão:

Bluetooth não conecta

A ferramenta verifica os componentes locais relacionados a Bluetooth e permite iniciar novamente a detecção do dispositivo.

Windows não inicia

Apresenta um procedimento orientado envolvendo:

Ambiente de Recuperação do Windows
Reparo de Inicialização
Desinstalação da atualização mais recente
Restauração do Sistema
Modo de Segurança
Tela preta depois do login

Inclui procedimentos para:

reiniciar o Windows Explorer;
verificar driver gráfico;
orientar reinicialização do subsistema gráfico.
Menu Iniciar ou Pesquisa travada

Permite reiniciar componentes relacionados ao:

Plain Text
Explorer
SearchHost
StartMenuExperienceHost
Explorador de Arquivos travando

Disponibiliza procedimentos de recuperação do Windows Explorer e diagnóstico dos componentes do sistema.

Tela Azul - BSOD

Auxilia na coleta de:

eventos críticos;
erros recentes;
código de falha;
arquivos Minidump.

O objetivo é auxiliar o diagnóstico, não apagar evidências importantes do problema.

PIN / Windows Hello

Apresenta procedimentos conservadores para problemas de autenticação.

Em ambientes corporativos também é recomendado verificar:

Microsoft Entra ID;
Microsoft Intune;
políticas do Windows Hello;
MFA;
data e hora;
conectividade.

A ferramenta evita excluir automaticamente dados de autenticação que poderiam gerar problemas adicionais.

Disco cheio ou uso em 100%

Disponibiliza diagnóstico de:

espaço utilizado;
espaço disponível;
processos;
arquivos temporários;
armazenamento.
VPN ou acesso remoto

Auxilia na análise de:

IP;
DNS;
adaptadores;
rotas;
serviços;
horário;
certificados;
conectividade.
Logs e coleta de diagnóstico

Algumas rotinas geram informações que podem ser utilizadas posteriormente pelo técnico.

É possível coletar dados como:

Plain Text
systeminfo
ipconfig
route
driverquery
tasklist
serviços
gpresult
dispositivos com erro

A ferramenta também possui uma opção de coleta completa de suporte, facilitando o envio de informações para análise de segundo nível.

Segurança

A ferramenta foi projetada para evitar algumas práticas comuns encontradas em scripts de otimização agressiva.

Por padrão, o projeto procura evitar:

desabilitar o Microsoft Defender;
desabilitar o Firewall;
desligar permanentemente serviços essenciais;
excluir drivers automaticamente;
alterar o BCD sem diagnóstico;
excluir arquivos críticos do Windows;
executar downloads automáticos;
abrir páginas externas;
alterar configurações corporativas sem confirmação.

Operações potencialmente impactantes apresentam uma confirmação antes da execução.

Requisitos

Recomendado:

Windows 11
Prompt de Comando
PowerShell
privilégios de Administrador

Algumas funções utilizam ferramentas nativas do Windows, entre elas:

Plain Text
DISM
SFC
CHKDSK
PNPUtil
PowerCfg
Netsh
IPConfig
GPResult
WEvtUtil
PowerShell
Como utilizar
Faça o download do arquivo .bat.
Salve localmente no computador.
Clique com o botão direito no arquivo.
Selecione Executar como administrador.
Escolha a cor das letras.
Selecione a categoria ou ferramenta desejada.
Leia as informações apresentadas antes de confirmar uma operação.

Para utilização completa, execute a ferramenta como Administrador.

Uso em ambiente corporativo

Antes de utilizar determinadas correções em equipamentos gerenciados, considere políticas aplicadas por:

Microsoft Intune;
Microsoft Entra ID;
Active Directory;
Group Policy;
Microsoft Defender for Endpoint;
BitLocker;
soluções de EDR;
ferramentas de gerenciamento de dispositivos.

Uma configuração que parece incorreta localmente pode estar sendo aplicada propositalmente pela organização.

Recomendações

A ferramenta deve ser utilizada como auxílio ao diagnóstico técnico, e não como substituta de análise.

Antes de executar reparos:

identifique o problema;
verifique eventos e sintomas;
confirme se o equipamento é corporativo;
considere políticas administrativas;
realize backup quando necessário;
execute a correção apropriada;
valide novamente o comportamento.
Compatibilidade
Sistema	SituaçãoWindows 11	✅ Principal plataforma
Windows 10	⚠️ Algumas funções podem funcionar
Windows Server	⚠️ Não é o objetivo principal
Linux	❌ Não suportado
macOS	❌ Não suportado
Contribuições

Sugestões de melhorias são bem-vindas.

Alguns exemplos:

novos diagnósticos;
novos problemas do Windows 11;
melhoria das rotinas existentes;
correções de compatibilidade;
melhorias na interface;
tratamento de erros;
novos relatórios para Help Desk.

Ao sugerir uma nova correção, dê preferência a ferramentas nativas e métodos documentados para o Windows.

Aviso

Esta ferramenta executa comandos administrativos que podem modificar configurações do Windows.

Utilize em ambiente de testes antes de distribuir em produção.

O responsável pelo uso deve avaliar cada procedimento de acordo com as políticas, configurações e requisitos da organização.

Ferramenta de Suporte - Windows 11

Diagnóstico • Manutenção • Reparação • Help Desk

Projeto desenvolvido para tornar atendimentos técnicos do Windows 11 mais rápidos, padronizados e práticos.
