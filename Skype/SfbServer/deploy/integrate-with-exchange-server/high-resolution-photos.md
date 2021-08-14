---
title: Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server
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
description: 'Zusammenfassung: Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.'
ms.openlocfilehash: 778603c2ae455fc20e3de6e6825c4cfe5b230eaa8b59323cbb7a25ff91bbca02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330499"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.
  
In Skype for Business Server können Fotos im Postfach Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online eines Benutzers gespeichert werden, das Fotogrößen von bis zu 648 x 648 Pixeln zulässt. Darüber hinaus können Exchange Server die Größe dieser Fotos für die Verwendung in verschiedenen Produkten nach Bedarf automatisch ändern. Dies bedeutet in der Regel drei verschiedene Fotogrößen und Auflösungen:
  
- 64 x 64 Pixel, die Für das Active Directory thumbnailPhoto-Attribut verwendete Größe. Wenn Sie ein Foto in Exchange Server hochladen, erstellt Exchange automatisch eine 64 x 64 Pixel große Version dieses Fotos und aktualisiert das ThumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass der Umgekehrte nicht zutrifft: Wenn Sie das ThumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange Postfach des Benutzers nicht automatisch aktualisiert.
    
- 96 x 96 Pixel für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business-Web-App und Skype for Business.
    
- 648 x 648 Pixel für die Verwendung in Skype for Business und Skype for Business-Web-App Skype for Business-Web-App.
    
> [!NOTE]
> Wenn Sie über die Ressourcen verfügen, wird empfohlen, 648 x 648 Fotos hochzuladen. die maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen bietet. Jedes JPEG-Foto mit einer Größe von 648 x 648 und einer Tiefe von 24 Bit ergibt eine Dateigröße von ca. 240 KB. Das bedeutet, dass Sie für alle vier Benutzerfotos ca. 1 MB Speicherplatz benötigen. 
  
Fotos mit hoher Auflösung, auf die mit Exchange Webdiensten zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur ihr eigenes Foto aktualisieren. Administratoren können das Foto jedoch für jeden Benutzer aktualisieren, indem sie die Exchange-Verwaltungsshell und eine Reihe von Windows PowerShell Befehlen wie die folgenden verwenden:
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Der erste Befehl im vorherigen Beispiel verwendet das `Get-Content` Cmdlet, um den Inhalt der Datei C:\Photos\Kenmyer.jpg zu lesen und diese Daten in einer Variablen mit dem Namen $photo zu speichern. Im zweiten Befehl wird das Cmdlet Exchange `Set-UserPhoto` verwendet, um das Foto hochzuladen und an das Benutzerkonto von Ken Myer anzufügen.
  
> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs referenzieren, wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen. Weitere Informationen finden Sie in der Dokumentation zum cmdlet Set-UserPhoto unter [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto)
  
Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Das Hochladen des Fotos führt einfach nur dazu, dass eine Vorschau des Fotos auf der Seite der Outlook Web App-Optionen angezeigt wird. Damit das Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl benutzt den Save-Parameter, um das Foto dem Benutzerkonto von Ken Myer zuzuweisen:
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann sich Ken Myer bei Skype for Business anmelden, **Optionen** auswählen und dann **"Mein Bild"** auswählen. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Wenn der Administrator das Foto mit Internet Explorer anzeigen kann, der Benutzer sein Foto jedoch nicht in Skype for Business kann ein Verbindungsproblem mit Exchange Webdiensten oder mit dem Exchange AutoErmittlungsdienst auftreten.
  
Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype for Business verfügbar zu machen. Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen und das `Set-UserPhoto` Cmdlet ausgeführt wurde.