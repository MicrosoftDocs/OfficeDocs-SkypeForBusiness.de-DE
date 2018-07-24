---
title: Skype für Business Server eine Server-zu-Server-Authentifizierungszertifikat zuweisen
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Zusammenfassung: Weisen Sie ein Zertifikat für die Server-zu-Server-Authentifizierung für Skype für Business Server.'
ms.openlocfilehash: 9bf2cf1ceaa43d5471d699a44f3e965b1bc5eda8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993757"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Skype für Business Server eine Server-zu-Server-Authentifizierungszertifikat zuweisen
**Zusammenfassung:** Weisen Sie ein Zertifikat für die Server-zu-Server-Authentifizierung für Skype für Business Server.
  
Um zu bestimmen, ob ein Server-zu-Server-Authentifizierungszertifikat bereits Skype für Business Server zugewiesen wurde, führen Sie den folgenden Befehl aus der Skype für Business Server-Verwaltungsshell:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Wenn keine Zertifikatinformationen zurückgegeben wird, dass Sie ein Zertifikat Tokenherausgebers zuweisen müssen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. Als allgemeine Regel kann Skype für Business Server-Zertifikat als OAuthTokenIssuer-Zertifikat verwendet werden. Beispielsweise kann Ihre Skype für Standardzertifikat Business Server auch als "oauthtokenissuer"-Zertifikat verwendet werden. (OAUthTokenIssuer-Zertifikat kann auch eine beliebige Webserverzertifikat, die den Namen der SIP-Domäne in das Feld Betreff enthält sein.) Die zwei primären Anforderungen für das Zertifikat für die Server-zu-Server-Authentifizierung verwendet werden, diese: 1) dasselbe Zertifikat muss konfiguriert werden, als "oauthtokenissuer"-Zertifikat auf allen Ihren Front-End-Servern; und 2) das Zertifikat muss mindestens 2048 Bit.
  
Wenn Sie über kein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat beziehen, das neue Zertifikat importieren und anschließend für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie angefordert und das neue Zertifikat abgerufen haben können einen Windows PowerShell-Befehl ähnlich importieren und dieses Zertifikat zuweisen Sie und klicken Sie dann melden Sie sich eine von den Front-End-Servern und verwenden:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Im vorstehenden Befehl den Pfad stellt Parameter den vollständigen Pfad zu der Zertifikatsdatei an, und der Parameter Password darstellt, das Kennwort, das dem Zertifikat zugewiesen wurde. Dieses Verfahren sollte nur einmal ausgeführt werden: die Skype für Business Server-Replikationsdienst erstellt dann automatisch eine Reihe von geplanten Aufgaben, die zu entschlüsseln und das Zertifikat für die Front-End-Server bereitstellen.
  
Alternativ können Sie ein vorhandenes Zertifikat als das Zertifikat für die Server-zu-Server-Authentifizierung verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als das Zertifikat für die Server-zu-Server-Authentifizierung verwendet werden.) Den folgenden zwei Windows PowerShell-Befehle das Standardzertifikat Thumbprint-Eigenschaft den Wert abzurufen, verwenden Sie diesen Wert zum Zertifikat des Server-zu-Server-Authentifizierungszertifikats machen:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Im vorstehenden Befehl wird das abgerufene Zertifikat so konfiguriert, dass als globale Server-zu-Server-Authentifizierungszertifikat fungieren. Dies bedeutet, dass das Zertifikat auf repliziert, und von den Front-End-Servern verwendet werden. Erneut, sollte dieser Befehl nur einmal und nur in einem von den Front-End-Servern ausgeführt werden. Obwohl alle Front-End-Server das gleiche Zertifikat verwenden müssen, sollten Sie nicht das OAuthTokenIssuer-Zertifikat auf jedem Front-End-Server konfigurieren. Stattdessen einmal konfigurieren Sie des Zertifikats, dann können Sie die Skype für Business Server Replication Server müssen Sie sicherstellen, dass das Zertifikat auf jedem Server kopieren.
  
Das Cmdlet "Set-CsCertificate" verwendet das Zertifikat fraglichen und sofort konfiguriert das Zertifikat als das aktuelle OAuthTokenIssuer-Zertifikat fungieren. (Skype für Business Server vermeidet eine Verbindung zwischen zwei Kopien eines Zertifikattyps: das aktuelle Zertifikat und die vorherige.) Wenn Sie das neue Zertifikat als "oauthtokenissuer"-Zertifikat fungieren sofort benötigen, sollten Sie das Set-CsCertificate-Cmdlet verwenden.
  
Mit dem Set-CsCertificate-Cmdlet können Sie auch ein neues Zertifikat „rollen“. Das „Rollen“ eines Zertifikats bedeutet einfach, dass Sie festlegen, dass ein neues Zertifikat ab einem bestimmten Zeitpunkt das aktuelle OAuthTokenIssuer-Zertifikat wird. Beispielsweise wird mit dem folgenden Befehl das Standardzertifikat abgerufen und dann dieses Zertifikat ab dem Mittwoch, 1. Juli 2015 als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Am 1. Juli 2015 wird das neue Zertifikat als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert und das "alte" OAuthTokenIssuer-Zertifikat wird als Vorheriges Zertifikat konfiguriert werden.
  
Wenn Sie nicht, verwenden Sie Windows PowerShell möchten können Sie die MMC-Konsole Zertifikate auch zum Exportieren eines Zertifikats aus einem Front-End-Server, und klicken Sie dann auf alle anderen Front-End-Servern importieren dasselbe Zertifikat verwenden. Dabei müssen Sie unbedingt den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.
  
> [!CAUTION]
> In diesem Fall muss das Verfahren auf jedem Front-End-Server ausgeführt werden. Beim Exportieren und Importieren von Zertifikaten auf diese Weise Skype für Business Server nicht, dass das Zertifikat auf jedem Front-End-Server repliziert werden. 
  
Nach dem Importieren des Zertifikats an den Front-End-Servern kann das Zertifikat dann mithilfe der Skype für Business Server-Bereitstellungsassistenten anstelle von Windows PowerShell zugewiesen werden. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungs-Assistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:
  
1. Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf **Skype für Business Server**und klicken Sie dann auf **Skype für Business Server-Bereitstellungs-Assistenten**.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **installieren oder aktualisieren Skype für Business Server-System**.
    
3. Klicken Sie auf die Skype für Business Server-Seite, auf die Schaltfläche **Ausführen** unter der Überschrift **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**. (Hinweis: Falls Sie auf diesem Computer bereits Zertifikate installiert haben, heißt die Schaltfläche nicht **Ausführen**, sondern **Erneut ausführen**.)
    
4. Wählen Sie im Zertifikat-Assistenten das Zertifikat **OAuthTokenIssuer** aus und klicken Sie auf **Zuweisen**.
    
5. Klicken Sie im Zertifikatzuweisungs-Assistenten auf der Seite **Zertifikatzuweisung** auf **Weiter**.
    
6. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie auf der Seite für die Zusammenfassung der Zertifikatzuweisung auf **Weiter**.
    
8. Klicken Sie auf der Seite „Befehle ausführen“ auf **Fertigstellen**.
    
9. Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.
    

