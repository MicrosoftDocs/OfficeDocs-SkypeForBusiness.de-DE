---
title: Konfigurieren der Verwendung hochauflösender Fotos in Skype for Business Server
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
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109801"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Konfigurieren der Verwendung hochauflösender Fotos in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren sie die Verwendung hochauflösender Fotos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.
  
In Skype for Business Server können Fotos im Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online-Postfach eines Benutzers gespeichert werden, wodurch Fotogrößen von bis zu 648 x 648 Pixeln möglich sind. Darüber hinaus können Exchange Server Fotos automatisch für die Verwendung in verschiedenen Produkten ändern. In der Regel bedeutet dies drei unterschiedliche Fotogrößen und Auflösungen:
  
- 64 x 64 Pixel, die größe, die für das Active Directory thumbnailPhoto-Attribut verwendet wird. Wenn Sie ein Foto in Exchange Server hochladen, erstellt Exchange automatisch eine Version von 64 Pixeln von 64 Pixeln dieses Fotos und aktualisiert das ThumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass das Gegenteil nicht der Fall ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange-Postfach des Benutzers nicht automatisch aktualisiert.
    
- 96 x 96 Pixel, für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App und Skype for Business.
    
- 648 x 648 Pixel für die Verwendung in Skype for Business und Skype for Business Web App Skype for Business Web App.
    
> [!NOTE]
> Wenn Sie über die Ressourcen verfügen, wird empfohlen, 648 x 648 Fotos hochzuladen. die maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen bietet. Jedes JPEG-Foto mit einer Größe von 648 x 648 und einer Tiefe von 24 Bit ergibt eine Dateigröße von ca. 240 KB. Das bedeutet, dass Sie pro 4 Benutzerfotos ca. 1 MB Speicherplatz benötigen. 
  
Hochauflösende Fotos, auf die mithilfe von #A0 zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur ihr eigenes Foto aktualisieren. Administratoren können das Foto jedoch für jeden Benutzer aktualisieren, indem sie die Exchange-Verwaltungsshell und eine Reihe von Windows PowerShell befehlen wie die folgenden verwenden:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Der erste Befehl im vorherigen Beispiel verwendet das Cmdlet, um den Inhalt der Datei C:\Photos\Kenmyer.jpg zu lesen und diese Daten in einer Variablen namens `Get-Content` $photo. Im zweiten Befehl wird das Exchange-Cmdlet verwendet, um das Foto hochzuladen und dieses Foto an das Benutzerkonto von `Set-UserPhoto` Ken Myer anfügen.
  
> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen. Weitere Informationen finden Sie in der Dokumentation Set-UserPhoto cmdlet unter [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto)
  
Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann sich Ken Myer bei Skype for Business anmelden, Optionen **auswählen** und dann Mein **Bild auswählen.** Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Wenn der Administrator das Foto mithilfe von Internet Explorer anzeigen kann, der Benutzer jedoch sein Foto nicht in Skype for Business anzeigen kann, kann es ein Verbindungsproblem mit Exchange-Webdiensten oder mit dem Exchange-AutoErmittlungsdienst gibt.
  
Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype for Business verfügbar zu machen. Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen und das `Set-UserPhoto` Cmdlet ausgeführt wurde.