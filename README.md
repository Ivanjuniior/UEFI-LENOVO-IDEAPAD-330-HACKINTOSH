<h1 align="center"> UEFI-LENOVO-IDEAPAD-330-HACKINTOSH </h1>
<h4>UEFI LENOVO IDEAPAD 330 81DE/81FD MacOS Big Sur/Monterey</h4>
Status do Projeto: :heavy_check_mark: :warning: (concluido, em desenvolvimento, etc)

<p>
  Este repositório, o readme e todos os arquivos que ele contém não serão atualizados, pois não estou mais usando meu hackintosh. Veja abaixo para qual versão do OpenCore o config.plist é aplicável e não o use com nenhuma outra versão.
Uma breve descrição sobre como configurar o macOS no Lenovo Ideapad 330s-15ikb 81F5.
Para o melhor sucesso, siga o guia vanilla OpenCore criado por Dortania para configurar tudo: https://dortania.github.io/OpenCore-Install-Guide/

Nenhum arquivo kext ou ACPI pré-construído será fornecido neste repositório. Por favor, use os links fornecidos para baixar cada arquivo.

Nota: Os arquivos marcados com (e) são essenciais para a inicialização, todos os outros estão fornecendo funcionalidades extras ou corrigindo problemas. Se você decidir não usar nenhum dos arquivos, você precisa fazer alterações de acordo com isso no config.plist

IMPORTANTE: Use os arquivos fornecidos por sua conta e risco. Não sou responsável se você quebrar seu laptop apenas copiando e colando tudo. Se o modelo do seu laptop for um pouco diferente, essa configuração pode não funcionar para você! Por favor, não copie e cole nada cegamente.
</p>
<h3 aling="left"> Hardware Especification </h3>

|Nome|Descrição|
| -------- |-------- |
|Notebook|Lenovo IdeaPad 330-15IKB 81DE|
|CPU|Intel(R) Core(TM) i3-8130U CPU @ 2.20GHz (KabyLake-R)|
|GPU|Intel Corporation UHD Graphics 620 (KabyLake-R)|
|HardDisk|SSD|
|Ethernet chipset|Realtek Semiconductor Co., Ltd. RTL8111 PCI Express Gigabit Ethernet Controller|
|WLAN/Bluetooth chipset|Intel Corporation Dual Band Wireless-AC 3165 Plus Bluetooth|
|Motherboard|Lenovo LNVNB161216|
|Audio codec|ALC3240|
... 

<h3 aling="left"> MacOS Suportados </h3>

|Nome|Versão|Descrição|
| -------- |-------- |-------- |
|Big Sur|11.6.2|Suportado|
|Monterey|12.0.1|Suportado|
... 

<h3 aling="left"> Observações </h3>

|Nome|Descrição|Versão|Status|
| -------- |-------- |-------- |-------- |
|opencore|suportado|0.7.7|:heavy_check_mark:|
|Audio|AppleALC|1.6.8|:heavy_check_mark:|
|Bluetooth|intelBluetoothFirmware|2.1.0|:heavy_check_mark:|
|Wireless|itlwm|2.1.0|:heavy_check_mark:|
|Ethernet|RealtekRTL8111|2.4.2|:heavy_check_mark:|
|Touchpad|VoodooPS2Controller|2.2.8|:heavy_check_mark:|
... 
- Wifi, Bluetooth, Airdrop, SideCar, Sleep, Wake, aceleração iGPU etc. tudo funcionando

<h3 aling="left">CONFIGURAR NA BIOS </h3>

- Configuration> Tecnologia Virtual Intel: Desativada(esta opção na verdade se refere à tecnologia "VT-x", que pode ser deixada ativada. VT-d não é acessível a partir do BIOS neste laptop)
- Configuration> Armazenamento> Modo Controlador: modo AHCI
- Security> Tecnologia Intel Platform Trust: desativada
- Security> Inicialização segura: desativada
- Boot> Boot Mode: UEFI (já deve ser UEFI, só para ter certeza)
- Boot> Inicialização USB: Ativado
- - todo o resto pode ser deixado como padrão

...
<h3 aling="left"> Notas </h3>

- [opencore dortania](http://dortania.github.io/)

...
