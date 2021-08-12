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
ms.openlocfilehash: b3d662dc3d0e18f0aefd1d8e643e09554fc39d652d31ac0bf8ed5540a5e34d8f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338149"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server
**Zusammenfassung:** Weisen Sie ein Server-zu-Server-Authentifizierungszertifikat für Skype for Business Server zu.
  
Führen Sie den folgenden Befehl aus der Skype for Business Server Verwaltungsshell aus, um festzustellen, ob Skype for Business Server bereits ein Server-zu-Server-Authentifizierungszertifikat zugewiesen wurde:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Tokenausstellerzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. In der Regel kann jedes Skype for Business Server Zertifikat als OAuthTokenIssuer-Zertifikat verwendet werden. Beispielsweise kann Ihr Skype for Business Server Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen Ihrer SIP-Domäne im Feld "Betreff" enthält.) Die beiden wichtigsten Anforderungen für das Zertifikat, das für die Server-zu-Server-Authentifizierung verwendet wird, sind: 1)dasselbe Zertifikat muss als OAuthTokenIssuer-Zertifikat auf allen Front-End-Servern konfiguriert werden. und, 2) das Zertifikat muss mindestens 2048 Bit sein.
  
Wenn Sie nicht über ein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat abrufen, das neue Zertifikat importieren und dieses Zertifikat dann für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und abgerufen haben, können Sie sich bei einem beliebigen Front-End-Server anmelden und einen Windows PowerShell Befehl wie diesen verwenden, um dieses Zertifikat zu importieren und zuzuweisen:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Im vorherigen Befehl stellt der Parameter "Path" den vollständigen Pfad zur Zertifikatdatei dar, und der Parameter "Password" stellt das Kennwort dar, das dem Zertifikat zugewiesen wurde. Dieses Verfahren sollte nur einmal ausgeführt werden: Der Skype for Business Server Replikationsdienst erstellt dann automatisch eine Reihe von geplanten Aufgaben, die das Zertifikat entschlüsseln und auf allen Front-End-Servern bereitstellen.
  
Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Das folgende paar Windows PowerShell Befehle rufen den Wert der Fingerabdruckeigenschaft des Standardzertifikats ab und verwenden dann diesen Wert, um das Standardzertifikat zum Server-zu-Server-Authentifizierungszertifikat zu machen:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Im vorherigen Befehl ist das abgerufene Zertifikat so konfiguriert, dass es als globales Server-zu-Server-Authentifizierungszertifikat fungiert. dies bedeutet, dass das Zertifikat auf allen Front-End-Servern repliziert und von diesen verwendet wird. Auch hier sollte dieser Befehl nur einmal und nur auf einem Ihrer Front-End-Server ausgeführt werden. Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das OAuthTokenIssuer-Zertifikat nicht auf jedem Front-End-Server konfigurieren. Konfigurieren Sie das Zertifikat stattdessen einmal, und lassen Sie den Skype for Business Server Replikationsserver das Kopieren dieses Zertifikats auf jeden Server übernehmen.
  
Das cmdlet Set-CsCertificate übernimmt das betreffende Zertifikat und konfiguriert dieses Zertifikat sofort so, dass es als aktuelles OAuthTokenIssuer-Zertifikat fungiert. (Skype for Business Server behält zwei Kopien eines Zertifikattyps bei: das aktuelle zertifikat und das vorherige Zertifikat.) Wenn Sie das neue Zertifikat benötigen, um sofort als OAuthTokenIssuer-Zertifikat zu fungieren, sollten Sie das Cmdlet Set-CsCertificate verwenden.
  
Sie können auch das Cmdlet Set-CsCertificate verwenden, um ein neues Zertifikat zu "rollen". "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. Beispielsweise ruft dieser Befehl das Standardzertifikat ab und konfiguriert dieses Zertifikat so, dass es ab dem 1. Juli 2015 als aktuelles OAuthTokenIssuer-Zertifikat übernommen wird:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Am 1. Juli 2015 wird das neue Zertifikat als aktuelles OAuthTokenIssuer-Zertifikat und das "alte" OAuthTokenIssuer-Zertifikat als vorheriges Zertifikat konfiguriert.
  
Wenn Sie Windows PowerShell nicht verwenden möchten, können Sie auch die MMC-Konsole "Zertifikate" verwenden, um ein Zertifikat von einem Front-End-Server zu exportieren und dann dasselbe Zertifikat auf allen anderen Front-End-Servern zu importieren. Wenn Sie dies tun, stellen Sie sicher, dass Sie den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.
  
> [!CAUTION]
> In diesem Fall muss die Prozedur auf jedem Front-End-Server ausgeführt werden. Beim Exportieren und Importieren von Zertifikaten auf diese Weise repliziert Skype for Business Server dieses Zertifikat nicht auf jedem Front-End-Server. 
  
Nachdem das Zertifikat auf alle Front-End-Server importiert wurde, kann dieses Zertifikat mithilfe des Skype for Business Server Bereitstellungs-Assistenten anstelle von Windows PowerShell zugewiesen werden. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungs-Assistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:
  
1. Klicken Sie auf "Start", auf "Alle Programme", auf **Skype for Business Server** und dann auf **Skype for Business Server Bereitstellungs-Assistenten.**
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **"Installieren" oder "Aktualisieren" Skype for Business Server System.**
    
3. Klicken Sie auf der seite Skype for Business Server unter der Überschrift **Schritt 3: Anfordern, Installieren oder Zuweisen** von Zertifikaten auf die Schaltfläche **"Ausführen".** (Hinweis: Wenn Sie bereits Zertifikate auf diesem Computer installiert haben, wird die Schaltfläche **"Ausführen"** mit der Bezeichnung **"Erneut ausführen"** bezeichnet.)
    
4. Wählen Sie im Zertifikat-Assistenten das **OAuthTokenIssuer-Zertifikat** aus, und klicken Sie dann auf **"Zuweisen".**
    
5. Klicken Sie im Zertifikatzuweisungs-Assistenten auf der Seite **"Zertifikatzuweisung"** auf **"Weiter".**
    
6. Wählen Sie auf der Seite **"Zertifikat Store"** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll, und klicken Sie dann auf **"Weiter".**
    
7. Klicken Sie auf der Seite Zusammenfassung der Zertifikatzuweisung auf **Weiter**.
    
8. Klicken Sie auf der Seite Befehle ausführen auf **Fertig stellen**.
    
9. Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.
    

