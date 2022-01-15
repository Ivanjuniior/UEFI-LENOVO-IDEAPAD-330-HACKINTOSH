<h1 align="center"> UEFI-LENOVO-IDEAPAD-330-HACKINTOSH </h1>
<h4>UEFI LENOVO IDEAPAD 330 81DE/81FD MacOS Big Sur/Monterey</h4>
Status do Projeto: :heavy_check_mark: :warning: (concluido, em desenvolvimento, etc)

<p>
  Este repositório, o readme e todos os arquivos que ele contém não serão atualizados, pois não estou mais usando meu hackintosh. Veja abaixo para qual versão do OpenCore o config.plist é aplicável e não o use com nenhuma outra versão.
Uma breve descrição sobre como configurar o macOS no Lenovo Ideapad 330s-15ikb 81DE/81FD/81F5.
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
... 

|Nome|Descrição|Curent Version|Fonte|Status|
| -------- |-------- |-------- |-------- |-------- |
|AppleALC|para entrada/saída de áudio nativo (usado com layoutid=14)|1.6.8|https://github.com/acidanthera/AppleALC|:heavy_check_mark:|
|AirportBrcmFixup|para WIFI em cartões WIFI não nativos|0.7.7|https://github.com/acidanthera/AirportBrcmFixup|:heavy_check_mark:|
|intelBluetoothFirmware|carregando firmware Bluetooth|2.1.0|https://github.com/acidanthera/BrcmPatchRAM|:heavy_check_mark:|
|BrightnessKeys|fazer F11 e F12 funcionarem como teclas de brilho|2.1.0|https://github.com/acidanthera/BrightnessKeys|:heavy_check_mark:|
|Lilu|basicamente necessário para quase todos os outros kexts funcionarem|2.4.2|https://github.com/acidanthera/Lilu|:heavy_check_mark:|
|VirtaulSMC + SMCProcessor + SMCBatteryManager|Virtualização SMC e leitura de sensores|2.2.8|https://github.com/acidanthera/VirtualSMC|:heavy_check_mark:|
|USBMap|mapeando as portas USB|...|https://github.com/corpnewt/USBMap|:heavy_check_mark:|
|VoodooI2C + VoodooI2CHID|trackpad|2.2.8|https://github.com/VoodooI2C/VoodooI2C|:heavy_check_mark:|
|VoodooPS2Controller|teclado (remova VoodooInput e VoodooPS2Trackpad da pasta Plugins)|...|https://github.com/acidanthera/VoodooPS2|:heavy_check_mark:|
|WhateverGreen |trackpad|...|https://github.com/acidanthera/WhateverGreen|:heavy_check_mark:|
|YogaSMC |ornece recursos adicionais para laptops Lenovo, como ThinkPad, Ideapad e Yoga (WIP)|...|https://github.com/zhen-zen/YogaSMC|:heavy_check_mark:|
... 
- Wifi, Bluetooth, Airdrop, SideCar, Sleep, Wake, aceleração iGPU etc. tudo funcionando
- se você quiser usar o seletor de BOT do OC, você precisa alterar o seguinte no config.plist: Misc> Boot> PickerMode: false

<h3 aling="left">CONFIGURAR NA BIOS </h3>

- Configuration> Tecnologia Virtual Intel: Desativada(esta opção na verdade se refere à tecnologia "VT-x", que pode ser deixada ativada. VT-d não é acessível a partir do BIOS neste laptop)
- Configuration> Armazenamento> Modo Controlador: modo AHCI
- Security> Tecnologia Intel Platform Trust: desativada
- Security> Inicialização segura: desativada
- Boot> Boot Mode: UEFI (já deve ser UEFI, só para ter certeza)
- Boot> Inicialização USB: Ativado
- - todo o resto pode ser deixado como padrão

...

<h3 aling="left">CONFIGURAR NO config.plist </h3>
- não se esqueça de configurar a seção Platforminfo/Generic/, isso é exclusivo para cada Hackintosh, pois contém SerialNumber, MLB, ROM. Use este guia
- para esta configuração é usado o SMBIOS do MacBookPro14,3 com i3-7020U/i5-8250U , pois é o mais próximo que podemos combinar com o i3-7020U/i5-8250U do Ideapad
- de acordo com o guia Dortania, um MacBookPro14,X é melhor, sinta-se à vontade para tentar usar esses SMBIOS e ver se obtém melhores resultados. Mais informações sobre como escolher o SMBIOS certo visite => http://dortania.github.io/
<h3 aling="left"> Fontes </h3>

- [opencore dortania](http://dortania.github.io/)

...
