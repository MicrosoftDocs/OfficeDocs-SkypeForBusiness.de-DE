---
title: Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Zusammenfassung: Konfigurieren Sie die Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.'
ms.openlocfilehash: 08db547dc9ead9d79a50cd17b4496826aa735369
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "37434910"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a>Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Skype for Business Server
 
**Zusammenfassung:** Konfigurieren Sie die Verwendung von Fotos mit hoher Auflösung in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online und Skype for Business Server.
  
In Skype for Business Server können Fotos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 oder Exchange Online-Postfach gespeichert werden, wodurch Foto Größen von bis zu 648 Pixeln um 648 Pixel möglich sind. Darüber hinaus kann Exchange Server die Größe dieser Fotos für die Verwendung in verschiedenen Produkten nach Bedarf automatisch ändern. Das bedeutet in der Regel drei verschiedene Foto Größen und-Auflösungen:
  
- 64 x 64 Pixel: die für das „thumbnailPhoto“-Attribut in Active Directory verwendete Größe. Wenn Sie ein Foto auf Exchange Server hochladen, erstellt Exchange automatisch eine 64 Pixel-Version von 64 Pixeln dieses Fotos und aktualisiert das thumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass umgekehrt nicht wahr ist: Wenn Sie das thumbnailPhoto-Attribut in Active Directory manuell aktualisieren, wird das Foto im Exchange-Postfach des Benutzers nicht automatisch aktualisiert.
    
- 96 Pixel von 96 Pixeln für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App und Skype for Business.
    
- 648 Pixel von 648 Pixeln für die Verwendung in Skype for Business und Skype for Business Web App Skype for Business Web App.
    
> [!NOTE]
> Sofern Sie ausreichende Ressourcen besitzen, wird empfohlen, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund 1 MB Speicherplatz benötigen. 
  
Fotos mit hoher Auflösung, auf die über Exchange-Webdienste zugegriffen wird, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen. Benutzer dürfen nur Ihr eigenes Foto aktualisieren. Administratoren können das Foto allerdings mit der Exchange-Verwaltungsshell und einer Reihe von Windows PowerShell-Befehlen aktualisieren, die dem folgenden ähneln:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Mit dem ersten Befehl im vorherigen Beispiel wird das `Get-Content` Cmdlet verwendet, um den Inhalt der Datei C:\Photos\Kenmyer.jpg zu lesen und diese Daten in einer Variablen mit dem Namen $Photo zu speichern. Im zweiten Befehl wird das Exchange-Cmdlet `Set-UserPhoto` verwendet, um das Foto hochzuladen und dieses Foto an das Benutzerkonto von Ken Myers anzufügen.
  
> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren. Weitere Informationen finden Sie in [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) der Dokumentation für das Cmdlet "Satz-UserPhoto".
  
Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Um zu überprüfen, ob das neue Foto dem Benutzerkonto zugewiesen wurde, kann Ken Myers sich bei Skype for Business anmelden, **Optionen**auswählen und dann **mein Bild**auswählen. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

Wenn der Administrator das Foto über Internet Explorer anzeigen kann, der Benutzer aber sein Foto in Skype for Business nicht anzeigen kann, liegt möglicherweise ein Verbindungsproblem mit Exchange-Webdiensten oder mit dem AutoErmittlungsdienst von Exchange vor.
  
Beachten Sie auch, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype for Business zur Verfügung zu stellen. Stattdessen ist das Foto sofort verfügbar, nachdem es hochgeladen wurde und das `Set-UserPhoto` Cmdlet ausgeführt wurde.
