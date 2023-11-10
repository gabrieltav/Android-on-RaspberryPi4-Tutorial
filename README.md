# Instalação do Android 13 na Raspberry Pi 4

## Passos

### Passo 1: Preparativos

Antes de começar, baixe a imagem do Android para Raspberry Pi 4 do [site oficial de KonstaKANG](https://konstakang.com/devices/rpi4/). Certifique-se de escolher a versão mais recente.


<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/1669fde9-3c3f-434b-b20e-75e10c44a58a" alt="Descrição da imagem" style="width:500px;">
</p>

Em seguida faça o download da imagem AOSP (Android 13)

<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/304fe0c3-65d7-4d1d-aed7-c3cf12c0d7c5" alt="Descrição da imagem" style="width:500px;">
</p>

Assim que o download for concluído. Atualize a imagem usando [Balena Etcher](https://etcher.balena.io/) ou pode usar outro gravador de imagem da sua preferência

<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/5e5b8d9c-b55b-45eb-ac3c-1d837873b665" alt="Descrição da imagem" style="width:500px;">
</p>

Aviso: certifique-se de selecionar o armazenamento correto para instalar o sistema operacional.

O flash pode demorar algum tempo dependendo da velocidade do dispositivo de armazenamento

Assim que o boot for concluído. Faça o download do arquivo [[AUTO]LiteGapps_arm64_13.0_v2.6_official.zip](https://sourceforge.net/projects/litegapps/files/litegapps/arm64/33/lite/v2.6/) é um pacote de aplicativos e serviços do Google que pode ser instalado em dispositivos Android personalizados com arquitetura ARM64 e Android 13. Ele é um pacote completo, com todos os aplicativos e serviços essenciais do Google, além de alguns aplicativos e serviços úteis extras.

<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/6fb67f77-293f-4ad2-bda1-01b15db22814" alt="Descrição da imagem" style="width:500px;">
</p>

Salve o arquivo baixado em um armazenamento USB separado. Vamos precisar dele depois...

Baixe também o arquivo zip de redimensionamento para estender o armazenamento em TWRP
<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/5866f87d-b18f-49a7-9d2c-7dd0e86a4480" alt="Descrição da imagem" style="width:500px;">
</p>

Salve o arquivo baixado em um armazenamento USB separado. Vamos precisar dele depois...
<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/e779012a-fb4e-4cab-8dda-840d576cccc6" alt="Descrição da imagem" style="width:500px;">
</p>

#### OBS: Nota: edite o arquivo config.tx se estiver usando um dispositivo USB. Esta etapa não é necessária se você estiver usando SDcard
O arquivo fica em: boot/config.tx
<p align="center">
  <img src="https://github.com/gabrieltav/Android-on-RaspberryPi4-Tutorial/assets/82974806/1d336ea5-30bf-4d44-b73f-78c96bf64433" alt="Descrição da imagem" style="width:500px;">
</p>

Encontre "Boot device" e sustitua tudo por:
```
# Boot device
#dtoverlay=android-sdcard
dtoverlay=android-usb
```

Ainda no arquivo config.txt. Você também pode fazer overclock de CPU e GPU para aumentar o desempenho.
```
# Overclock
over_voltage=6
arm_freq=2000
gpu_freq=700
```

#### Feito isso, salve as alterações e ejete o dispositivo.
