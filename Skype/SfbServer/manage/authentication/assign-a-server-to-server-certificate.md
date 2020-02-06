---
title: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 4689306e0fb8cd7b7c8ce67f74c6ddb65db44f13
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818857"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Skype for Business Server
**Zusammenfassung:** Zuweisen eines Server-zu-Server-Authentifizierungszertifikats für Skype for Business Server.
  
Wenn Sie feststellen möchten, ob einem Server-zu-Server-Authentifizierungszertifikat bereits Skype for Business Server zugewiesen wurde, führen Sie den folgenden Befehl aus der Skype for Business Server-Verwaltungsshell aus:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Token-Ausstellerzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. In der Regel kann jedes Skype for Business Server-Zertifikat als Ihr OAuthTokenIssuer-Zertifikat verwendet werden. So kann beispielsweise das Standardzertifikat von Skype for Business Server auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen Ihrer SIP-Domäne im Feld Betreff enthält.) Die primären beiden Anforderungen für das für die Server-zu-Server-Authentifizierung verwendete Zertifikat sind: 1) dasselbe Zertifikat muss auf allen Front-End-Servern als OAuthTokenIssuer-Zertifikat konfiguriert sein. und 2) das Zertifikat muss mindestens 2048 Bits aufweisen.
  
Wenn Sie über kein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat beziehen, das neue Zertifikat importieren und anschließend für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und erhalten haben, können Sie sich bei einem der Front-End-Server anmelden und einen Windows PowerShell-Befehl wie den folgenden verwenden, um das Zertifikat zu importieren und zuzuweisen:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Im vorangehenden Befehl stellt der path-Parameter den vollständigen Pfad zur Zertifikatsdatei dar, und der Parameter Password steht für das Kennwort, das dem Zertifikat zugewiesen wurde. Diese Vorgehensweisesollte nur einmal ausgeführt werden: der Skype for Business Server-Replikationsdienst erstellt dann automatisch eine Reihe von geplanten Aufgaben, die das Zertifikat für alle Ihre Front-End-Server entschlüsseln und bereitstellen.
  
Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Das folgende Paar von Windows PowerShell-Befehlen Ruft den Wert der Eigenschaft "Fingerabdruck" des Standardzertifikats ab und verwendet diesen Wert, um das Standardzertifikat zum Server-zu-Server-Authentifizierungszertifikat zu machen:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Im vorhergehenden Befehl ist das abgerufene Zertifikat so konfiguriert, dass es als globales Server-zu-Server-Authentifizierungszertifikat dient. Das bedeutet, dass das Zertifikat an alle Ihre Front-End-Server repliziert und von diesen verwendet wird. Dieser Befehl sollte erneut nur einmal und nur auf einem der Front-End-Server ausgeführt werden. Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das OAuthTokenIssuer-Zertifikat nicht auf jedem Front-End-Server konfigurieren. Konfigurieren Sie stattdessen das Zertifikat einmal, und lassen Sie den Skype for Business Server-Replikationsserver dafür sorgen, dass das Zertifikat auf jeden Server kopiert wird.
  
Das Cmdlet "festlegen-CsCertificate" übernimmt das fragliche Zertifikat und konfiguriert dieses Zertifikat sofort so, dass es als Aktuelles OAuthTokenIssuer-Zertifikat fungiert. (Skype for Business Server speichert zwei Kopien eines Zertifikatstyps: das aktuelle Zertifikat und das vorherige Zertifikat.) Wenn Sie möchten, dass das neue Zertifikat sofort als OAuthTokenIssuer-Zertifikat fungiert, sollten Sie das Cmdlet "CsCertificate" verwenden.
  
Mit dem Set-CsCertificate-Cmdlet können Sie auch ein neues Zertifikat „rollen“. Das „Rollen“ eines Zertifikats bedeutet einfach, dass Sie festlegen, dass ein neues Zertifikat ab einem bestimmten Zeitpunkt das aktuelle OAuthTokenIssuer-Zertifikat wird. Beispielsweise wird mit dem folgenden Befehl das Standardzertifikat abgerufen und dann dieses Zertifikat ab dem Mittwoch, 1. Juli 2015 als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Am 1. Juli 2015 wird das neue Zertifikat als Aktuelles OAuthTokenIssuer-Zertifikat konfiguriert, und das "alte" OAuthTokenIssuer-Zertifikat wird als Vorheriges Zertifikat konfiguriert.
  
Wenn Sie Windows PowerShell nicht verwenden möchten, können Sie auch die MMC-Konsole Zertifikate verwenden, um ein Zertifikat von einem Front-End-Server zu exportieren und dieses Zertifikat dann auf allen anderen Front-End-Servern zu importieren. Dabei müssen Sie unbedingt den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.
  
> [!CAUTION]
> In diesem Fall muss die Prozedur auf jedem Front-End-Server ausgeführt werden. Wenn Sie Zertifikate auf diese Weise exportieren und importieren, wird das Zertifikat von Skype for Business Server nicht auf jeden Front-End-Server repliziert. 
  
Nachdem das Zertifikat auf alle Ihre Front-End-Server importiert wurde, kann dieses Zertifikat über den Skype for Business Server-Bereitstellungs-Assistenten anstelle von Windows PowerShell zugewiesen werden. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungs-Assistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:
  
1. Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Bereitstellungs-Assistent**.
    
2. Klicken Sie im Bereitstellungs-Assistenten auf **Skype for Business Server-System installieren oder aktualisieren**.
    
3. Klicken Sie auf der Seite Skype for Business Server unter der Überschrift **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf die Schaltfläche **Ausführen** . (Hinweis: Falls Sie auf diesem Computer bereits Zertifikate installiert haben, heißt die Schaltfläche nicht **Ausführen**, sondern **Erneut ausführen**.)
    
4. Wählen Sie im Zertifikat-Assistenten das Zertifikat **OAuthTokenIssuer** aus und klicken Sie auf **Zuweisen**.
    
5. Klicken Sie im Zertifikatzuweisungs-Assistenten auf der Seite **Zertifikatzuweisung** auf **Weiter**.
    
6. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie auf der Seite für die Zusammenfassung der Zertifikatzuweisung auf **Weiter**.
    
8. Klicken Sie auf der Seite „Befehle ausführen“ auf **Fertigstellen**.
    
9. Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.
    

