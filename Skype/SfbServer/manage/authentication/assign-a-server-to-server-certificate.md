---
title: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Zusammenfassung: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats für Skype for Business Server.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828505"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server
**Zusammenfassung:** Weisen Sie ein Server-zu-Server-Authentifizierungszertifikat für Skype for Business Server zu.
  
Um festzustellen, ob Skype for Business Server bereits ein Server-zu-Server-Authentifizierungszertifikat zugewiesen wurde, führen Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Tokenherausgeberzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. In der Regel kann jedes Skype for Business #A0 als #A1 verwendet werden. Beispielsweise kann Ihr Skype for Business Server-Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen Ihrer SIP-Domäne im Feld "Betreff" enthält.) Die beiden wichtigsten Anforderungen für das Zertifikat, das für die Server-zu-Server-Authentifizierung verwendet wird, sind: 1) Dasselbe Zertifikat muss auf allen Front-End-Servern als #A0 konfiguriert werden. und 2) Das Zertifikat muss mindestens 2048 Bit lang sein.
  
Wenn Sie nicht über ein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat abrufen, das neue Zertifikat importieren und dieses Zertifikat dann für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und erhalten haben, können Sie sich bei einem beliebigen Ihrer Front-End-Server anmelden und einen Windows PowerShell-Befehl wie diesen verwenden, um das Zertifikat zu importieren und zuzuordnen:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Im vorstehenden Befehl stellt der Parameter "Path" den vollständigen Pfad zur Zertifikatdatei dar, und der Parameter "Password" stellt das Kennwort dar, das dem Zertifikat zugewiesen wurde. Dieses Verfahren sollte nur einmal ausgeführt werden: Der Skype for Business Server-Replikationsdienst erstellt dann automatisch eine Reihe geplanter Aufgaben, die das Zertifikat entschlüsseln und auf allen Front-End-Servern bereitstellen.
  
Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Die folgenden Windows PowerShell rufen den Wert der Eigenschaft "Thumbprint" des Standardzertifikats ab und verwenden dann diesen Wert, um das Standardzertifikat zum Server-zu-Server-Authentifizierungszertifikat zu machen:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Im vorstehenden Befehl ist das abgerufene Zertifikat so konfiguriert, dass es als globales Server-zu-Server-Authentifizierungszertifikat funktioniert. das bedeutet, dass das Zertifikat auf alle Front-End-Server repliziert und von diesen verwendet wird. Auch hier sollte dieser Befehl nur einmal und nur auf einem Ihrer Front-End-Server ausgeführt werden. Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das Zertifikat OAuthTokenIssuer nicht auf jedem Front-End-Server konfigurieren. Konfigurieren Sie stattdessen das Zertifikat einmal, und lassen Sie den Skype for Business Server-Replikationsserver das Zertifikat auf jeden Server kopieren.
  
Das Set-CsCertificate verwendet das in Frage gestellte Zertifikat und konfiguriert dieses Zertifikat sofort als das aktuelle OAuthTokenIssuer-Zertifikat. (Skype for Business Server behält zwei Kopien eines Zertifikattyps bei: das aktuelle Zertifikat und das vorherige Zertifikat.) Wenn Das neue Zertifikat sofort als das OAuthTokenIssuer-Zertifikat fungieren soll, sollten Sie das Set-CsCertificate verwenden.
  
Sie können auch das cmdlet Set-CsCertificate, um ein neues Zertifikat zu "rollen". "Rolling" eines Zertifikats bedeutet einfach, dass Sie ein neues Zertifikat so konfigurieren, dass es zu einem bestimmten Zeitpunkt zum aktuellen OAuthTokenIssuer-Zertifikat wird. Mit dem folgenden Befehl wird beispielsweise das Standardzertifikat abgerufen und dann so konfiguriert, dass es ab dem 1. Juli 2015 als aktuelles OAuthTokenIssuer-Zertifikat verwendet wird:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Am 1. Juli 2015 wird das neue Zertifikat als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert, und das "alte" OAuthTokenIssuer-Zertifikat wird als vorheriges Zertifikat konfiguriert.
  
Wenn Sie Windows PowerShell können Sie auch die Zertifikat-MMC-Konsole verwenden, um ein Zertifikat von einem Front-End-Server zu exportieren und dann dasselbe Zertifikat auf allen anderen Front-End-Servern zu importieren. Wenn Sie dies tun, stellen Sie sicher, dass Sie den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.
  
> [!CAUTION]
> In diesem Fall muss das Verfahren auf jedem Front-End-Server ausgeführt werden. Beim Exportieren und Importieren von Zertifikaten auf diese Weise repliziert Skype for Business Server dieses Zertifikat nicht auf jeden Front-End-Server. 
  
Nachdem das Zertifikat auf alle Front-End-Server importiert wurde, kann dieses Zertifikat mithilfe des Skype for Business Server-Bereitstellungs-Assistenten zugewiesen werden, anstatt Windows PowerShell. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungsassistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungsassistent installiert wurde:
  
1. Klicken Sie auf "Start", "Alle Programme", **"Skype for Business Server"** und dann auf **"Skype for Business Server-Bereitstellungs-Assistent".**
    
2. Klicken Sie im Bereitstellungsassistenten auf **"Skype for Business Server System installieren oder aktualisieren".**
    
3. Klicken Sie auf der Seite  Skype for Business Server unter der Überschrift Schritt 3 auf die Schaltfläche "Ausführen": Zertifikate **anfordern, installieren oder zuweisen.** (Hinweis: Wenn Sie bereits Zertifikate auf diesem  Computer installiert haben, wird die Schaltfläche "Ausführen" mit der Bezeichnung "Erneut **ausführen" bezeichnet.)**
    
4. Wählen Sie im Zertifikat-Assistenten das **OAuthTokenIssuer-Zertifikat** aus, und klicken Sie dann auf **"Zuweisen".**
    
5. Klicken Sie im Assistenten für die Zertifikatzuweisung auf der Seite **"Zertifikatzuweisung"** auf **"Weiter".**
    
6. Wählen Sie **auf der Seite Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll, und klicken Sie dann auf **"Weiter".**
    
7. Klicken Sie auf der Seite Zusammenfassung der Zertifikatzuweisung auf **Weiter**.
    
8. Klicken Sie auf der Seite Befehle ausführen auf **Fertig stellen**.
    
9. Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.
    

