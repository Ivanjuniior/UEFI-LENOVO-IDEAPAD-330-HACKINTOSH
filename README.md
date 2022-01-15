<h1 align="center"> UEFI-LENOVO-IDEAPAD-330-HACKINTOSH </h1>
<h4>UEFI LENOVO IDEAPAD 330 81DE/81FD MacOS Big Sur/Monterey</h4>
Status do Projeto: :heavy_check_mark: :warning: (concluido, em desenvolvimento, etc)

<p>
  Este repositório, o readme e todos os arquivos que ele contém não serão atualizados, pois os dados aqui fornecidos é para aquelas pesssoas que querem testar o hackintosh. Veja abaixo para qual versão do OpenCore o config.plist é aplicável e não o use com nenhuma outra versão.
Uma breve descrição sobre como configurar o macOS no Lenovo Ideapad 330s-15ikb 81DE/81FD/81F5.
Para o melhor sucesso, siga o guia vanilla OpenCore criado por Dortania para configurar tudo: https://dortania.github.io/OpenCore-Install-Guide/

  <b><h4>:warning: IMPORTANTE: :warning:</h4>
  Use os arquivos fornecidos por sua conta e risco. Não sou responsável se você quebrar seu laptop apenas copiando e colando tudo. Se o modelo do seu laptop for um pouco diferente, essa configuração pode não funcionar para você! Por favor, não copie e cole nada cegamente.
  </b></p>
<h3 aling="left"> Hardware Utilizado e Especifico </h3>

|Nome|Descrição|
| -------- |-------- |
|Notebook|Lenovo IdeaPad 330-15IKB 81FD|
|CPU|Intel(R) Core(TM) i3-8130U CPU @ 2.20GHz (KabyLake-R)|
|GPU|Intel Corporation UHD Graphics 620 (KabyLake-R)|
|HardDisk|SSD de sua escolha|
|Ethernet chipset|Realtek Semiconductor Co., Ltd. RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller|
|WLAN/Bluetooth chipset|Intel Corporation Dual Band Wireless-AC 3165 Plus Bluetooth|
|Motherboard|Lenovo LNVNB161216|
|Audio codec|ALC3240|
... 

<h3 aling="left"> MacOS Testados </h3>

|Nome|Versão|Descrição|
| -------- |-------- |-------- |
|Big Sur|11.6.2|:heavy_check_mark:|
|Monterey|12.0.1|:heavy_check_mark:|
... 

<h3 aling="left"> Observações </h3>

|Nome|Descrição|Versão|Status|
| -------- |-------- |-------- |-------- |
|opencore|suportado|0.7.7|:heavy_check_mark:|
... 

|Nome|Descrição|Versão instalada|Fonte|Status|
| -------- |-------- |-------- |-------- |-------- |
|AppleALC|para entrada/saída de áudio nativo (usado com layoutid=14)|1.6.8|[AppleALC](https://github.com/acidanthera/AppleALC)|:heavy_check_mark:|
|AirportBrcmFixup|para WIFI em cartões WIFI não nativos|2.1.3|[AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup)|:heavy_check_mark:|
|intelBluetoothFirmware|carregando firmware Bluetooth|2.1.0|[intelBluetoothFirmware](https://github.com/acidanthera/BrcmPatchRAM)|:heavy_check_mark:|
|Lilu|basicamente necessário para quase todos os outros kexts funcionarem|1.5.9|[Lilu](https://github.com/acidanthera/Lilu)|:heavy_check_mark:|
|VirtaulSMC + SMCProcessor + SMCBatteryManager|Virtualização SMC e leitura de sensores|1.2.9|[VirtaulSMC](https://github.com/acidanthera/VirtualSMC)|:heavy_check_mark:|
|USBMap|mapeando as portas USB|...|[USBMap](https://github.com/corpnewt/USBMap) ou [Gabriel Luchina](https://www.youtube.com/watch?v=Dz9QxbNlzm4&t=784s&ab_channel=GabrielLuchina)|:heavy_check_mark:|
|Voodool2C + VoodooI2CHID|trackpad|2.6.5|[Voodool2C](https://github.com/VoodooI2C/VoodooI2C)|:heavy_check_mark:|
|Voodooinput|trackpad|1.1.1|[Voodooinput](https://github.com/VoodooI2C/VoodooI2C)|:heavy_check_mark:|
|VoodooPS2Controller|teclado (remova VoodooInput e VoodooPS2Trackpad da pasta Plugins)|2.2.8|[VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2)|:heavy_check_mark:|
|WhateverGreen|trackpad|1.5.6|[WhateverGreen](https://github.com/acidanthera/WhateverGreen)|:heavy_check_mark:|
|YogaSMC|ornece recursos adicionais para laptops Lenovo, como ThinkPad, Ideapad e Yoga (WIP)|1.5.1|[YogaSMC](https://github.com/zhen-zen/YogaSMC)|:heavy_check_mark:|
... 
- Wifi, Bluetooth, Airdrop, SideCar, Sleep, Wake, aceleração iGPU etc. tudo funcionando
- se você quiser usar o seletor de BOT do OC, você precisa alterar o seguinte no config.plist: Misc> Boot> PickerMode: false
- Importante fazer o mapeamento das portas USBs, deixei 2 links acima ensinando como fazer o mapeamento, vou mostrar abaixo como ficou o mapeamento das portas USBs do modelo 81FD.

![Captura de Tela 2022-01-15 às 14 00 29](https://user-images.githubusercontent.com/97719298/149637458-3432bdf9-f653-4b7f-9eb6-359c0d1b7422.png)


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

- não se esqueça de configurar a seção Platforminfo/Generic/, isso é exclusivo para cada Hackintosh, pois contém SerialNumber, MLB, ROM. [Use este guia ](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#platforminfo)
- para esta configuração é usado o SMBIOS do MacBookPro14,3 com i3-7020U/i5-8250U , pois é o mais próximo que podemos combinar com o i3-7020U/i5-8250U do Ideapad
- de acordo com o guia Dortania, um MacBookPro14,X é melhor, sinta-se à vontade para tentar usar esses SMBIOS e ver se obtém melhores resultados. [Mais informações sobre como escolher o SMBIOS certo.](http://dortania.github.io/)
- SMBIOS DE EXEMPLO:
- - (gerem seu proprio SMBIOS.

-   #######################################################
-  #               MacBookPro14,1 SMBIOS Info            #
- #######################################################

- Type:         MacBookPro14,1
- Serial:       XXXXXXXXXXXX
- Board Serial: XXXXXXXXXXXXXXXXX
- SmUUID:       XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX

...
<h3 aling="left"> Fontes </h3>

- [opencore dortania](http://dortania.github.io/)

...
