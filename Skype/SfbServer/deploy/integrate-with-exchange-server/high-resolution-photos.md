---
title: Konfigurieren der Verwendung von hochauflösenden Fotos in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: 'Zusammenfassung: Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server 2015.'
ms.openlocfilehash: 43ca3ca0444339ff61811c8aad5860989e45ca33
ms.sourcegitcommit: faea19005301c56a081b6e6157965becac76ec2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server-2015"></a>Konfigurieren der Verwendung von hochauflösenden Fotos in Skype for Business Server 2015
 
**Zusammenfassung:** Konfigurieren Sie die Verwendung von hoch auflösenden Fotos in Exchange Server 2016 oder Exchange Server 2013 und Skype für Business Server 2015.
  
In Skype für Business Server 2015 können Fotos in Exchange Server 2016 oder Exchange Server 2013 Postfach eines Benutzers, die bis zu 648 x 648 Pixel Foto Größen ermöglicht gespeichert werden. Exchange Server darüber hinaus können diese Fotos in anderen Produkten automatisch angepasst, je nach Bedarf. In der Regel bedeutet, dass drei verschiedenen Foto Größen und Lösungen:
  
- 64 x 64 Pixel: die für das thumbnailPhoto-Attribut in Active Directory verwendete Größe. Wenn Sie ein Foto in Exchange Server hochladen, Exchange automatisch ein 64 Pixel von 64 Pixel-Version dieses Foto erstellen und aktualisieren ThumbnailPhoto-Attribut des Benutzers. Beachten Sie jedoch, dass die Umkehrung nicht true ist: Wenn Sie das Attribut ThumbnailPhoto in Active Directory manuell aktualisieren das Foto im Exchange-Postfach des Benutzers wird nicht automatisch aktualisiert werden.
    
- 96 x 96 Pixel, für die Verwendung in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype für Business Web App und Skype für Unternehmen.
    
- 648 x 648 Pixel für verwenden in Skype für Unternehmen und Skype für Business Web App Skype für Web-Geschäfts-App.
    
> [!NOTE]
> Sofern Sie ausreichende Ressourcen besitzen, wird empfohlen, Fotos im Format 648 x 648 Pixel hochzuladen. Dies sorgt für eine maximale Auflösung und optimale Bildqualität in allen Office 2013-Anwendungen. Ein JPEG-Foto mit 648 x 648 Pixel und einer Tiefe von 24 Bit ergibt eine Datei mit einer Größe von rund 240 KB. Dies bedeutet, dass Sie für je vier Benutzerfotos rund 1 MB Speicherplatz benötigen. 
  
Fotos mit hoher Auflösung, die mithilfe der Exchange-Webdienste zugegriffen werden, können von Benutzern hochgeladen werden, die Outlook 2013 Web App ausführen; Benutzer dürfen nur eigene Foto zu aktualisieren. Administratoren können das Foto für jeden Benutzer jedoch mithilfe der Exchange-Verwaltungsshell und eine Reihe von Windows PowerShell-Befehle wie folgt aktualisieren:
  
```
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData -Preview $photo -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Der erste Befehl im vorstehenden Beispiel verwendet die `Get-Content` -Cmdlet zum Lesen Sie den Inhalt der Datei C:\Photos\Kenmyer.jpg, und speichern diese Daten in einer Variablen mit dem Namen $photo. Im zweiten Befehl, mit dem Exchange-Cmdlet `Set-UserPhoto` wird verwendet, um das Foto hochladen, und fügen Sie dieses Foto Ken Myers Benutzerkonto.
  
> [!NOTE]
> In diesem Beispiel wird der Active Directory-Anzeigename von Ken Myer als Benutzerkontoidentität verwendet. Sie können ein Benutzerkonto auch über andere IDs wie die SMTP-Adresse des Benutzers oder dessen Benutzerprinzipalnamen referenzieren. Finden Sie in der Dokumentation für das Cmdlet Set-UserPhoto bei [https://go.microsoft.com/fwlink/p/?LinkId=268536](https://go.microsoft.com/fwlink/p/?LinkId=268536) Weitere Informationen
  
Das Hochladen des Fotos entspricht keiner Zuweisung des Fotos zu Ken Myers Benutzerkonto. Durch das Hochladen wird einfach eine Vorschau dieses Fotos auf der Seite der Outlook Web App-Optionen angezeigt. Damit dieses Foto dem Benutzerkonto zugewiesen wird, muss der Benutzer auf der Seite mit den Optionen auf **Speichern** klicken oder der Administrator muss den dritten Befehl des Beispiels ausführen. Dieser dritte Befehl weist das Foto mithilfe des Parameters „Save“ dem Benutzerkonto von Ken Myer zu:
  
```
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

Um sicherzustellen, dass das Benutzerkonto ein neue Foto zugewiesen wurde, kann Ken Myer Skype für Unternehmen, wählen Sie **Optionen**, und wählen Sie **Mein Bild**anmelden. Das neu hochgeladene Foto sollte dann als Kens persönliches Foto angezeigt werden. Alternativ können Administratoren die Fotos aller Benutzer prüfen, indem sie den Internet Explorer starten und zu einer URL der folgenden Art navigieren:
  
```
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&amp;size=HR648x648
```

Wenn der Administrator kann das Foto mit Internet Explorer anzeigen, aber der Benutzer nicht sein eigenes Foto, in Skype für Unternehmen anzeigen kann kann ein Verbindungsproblem mit Exchange-Webdienste oder mit der Exchange-AutoErmittlungsdienst vorhanden sein.
  
Beachten Sie außerdem, dass keine zusätzliche Konfiguration erforderlich ist, um dieses Foto in Skype für Unternehmen verfügbar zu machen. Stattdessen das Foto werden sofort zur Verfügung stehen, nachdem er hochgeladen wurde und die `Set-UserPhoto` Cmdlet ausgeführt wurde.
