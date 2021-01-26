---
title: Konfigurieren der Verwendung von hochauflösenden Fotos in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Zusammenfassung: Konfigurieren der Verwendung hochauflösender Fotos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.'
ms.openlocfilehash: c55e5a90e222ea024dd63f72b26627141b2f113e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834005"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Konfigurieren der Verwendung von hochauflösenden Fotos in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Verwendung hochauflösender Fotos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.
  
In Skype for Business Server können Fotos im Exchange Server 2019-, Exchange Server 2016-, Exchange Server 2013- oder Exchange Online-Postfach eines Benutzers gespeichert werden, das Fotogrößen von bis zu 648 x 648 Pixeln ermöglicht. Darüber hinaus können Exchange Server fotos automatisch ändern, damit sie bei Bedarf in verschiedenen Produkten verwendet werden können. In der Regel bedeutet dies drei verschiedene Fotogrößen und Auflösungen:
  
- 64 x 64 Pixel, die größe, die für das Active Directory thumbnailPhoto-Attribut verwendet wird. Wenn Sie ein Foto in Exchange Server hochladen, erstellt Exchange automatisch eine Version von 64 pixeln zu 64 Pixeln des Fotos und aktualisiert das thumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass das Gegenteil nicht der Fall ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange-Postfach des Benutzers nicht automatisch aktualisiert.
    
- 96 x 96 Pixel für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App und Skype for Business.
    
- 648 x 648 Pixel für die Verwendung in Skype for Business und Skype for Business Web App Skype for Business Web App.
    
> [!NOTE]
> Wenn Sie über die Ressourcen verfügen, wird empfohlen, 648 x 648 Fotos hochzuladen. die maximale Auflösung und optimale Bildqualität in einer der Office 2013-Anwendungen bietet. Jedes JPEG-Foto mit einer Größe von 648 x 648 und einer Tiefe von 24 Bit ergibt eine Dateigröße von ca. 240 KB. Dies bedeutet, dass Sie pro 4 Benutzerfotos ca. 1 MB Speicherplatz benötigen. 
  
Hochauflösende Fotos, auf die über #A0 zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur ihr eigenes Foto aktualisieren. Administratoren können jedoch das Foto für jeden Benutzer aktualisieren, indem sie die Exchange-Verwaltungsshell und eine Reihe von Befehlen Windows PowerShell wie die folgenden verwenden:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Der erste Befehl im vorherigen Beispiel verwendet das Cmdlet, um den Inhalt der Datei C:\Photos\Kenmyer.jpg zu lesen und diese Daten in einer Variablen mit dem Namen `Get-Content` $photo. Im zweiten Befehl wird das Exchange-Cmdlet verwendet, um das Foto hochzuladen und an das Benutzerkonto von `Set-UserPhoto` Ken Myer anfügen.
  
> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen. Weitere Informationen finden Sie in der Dokumentation Set-UserPhoto cmdlet. [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536)
  
Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann sich Ken Myer bei Skype for Business anmelden, Optionen auswählen **und** dann "Mein Bild" **auswählen.** Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer sein Foto jedoch nicht in Skype for Business anzeigen kann, liegt möglicherweise ein Verbindungsproblem mit den Exchange-Webdiensten oder dem Exchange-AutoErmittlungsdienst vor.
  
Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype for Business verfügbar zu machen. Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen und das `Set-UserPhoto` Cmdlet ausgeführt wurde.
