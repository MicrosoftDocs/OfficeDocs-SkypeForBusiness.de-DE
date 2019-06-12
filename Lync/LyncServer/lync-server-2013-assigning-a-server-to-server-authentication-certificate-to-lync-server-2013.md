---
title: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63d4e5e3ac8c544e83ab9cfb8f82a5c70f86131b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-24_

Führen Sie den folgenden Befehl in der lync Server 2013-Verwaltungsshell aus, um zu ermitteln, ob ein Server-zu-Server-Authentifizierungszertifikat bereits Microsoft lync Server 2013 zugewiesen wurde:

    Get-CsCertificate -Type OAuthTokenIssuer

Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Token-Ausstellerzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. In der Regel kann jedes lync Server 2013-Zertifikat als OAuthTokenIssuer-Zertifikat verwendet werden. So kann beispielsweise das Standardzertifikat von lync Server 2013 auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen Ihrer SIP-Domäne im Feld Betreff enthält.) Die primären beiden Anforderungen für das für die Server-zu-Server-Authentifizierung verwendete Zertifikat sind: 1) dasselbe Zertifikat muss auf allen Front-End-Servern als OAuthTokenIssuer-Zertifikat konfiguriert sein. und 2) das Zertifikat muss mindestens 2048 Bits aufweisen.

Wenn Sie über kein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat beziehen, das neue Zertifikat importieren und anschließend für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und erhalten haben, können Sie sich bei einem der Front-End-Server anmelden und einen Windows PowerShell-Befehl wie den folgenden verwenden, um das Zertifikat zu importieren und zuzuweisen:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Im vorangehenden Befehl stellt der path-Parameter den vollständigen Pfad zur Zertifikatsdatei dar, und der Parameter Password steht für das Kennwort, das dem Zertifikat zugewiesen wurde. Diese Vorgehensweisesollte nur einmal ausgeführt werden: der Replikationsdienst von lync Server erstellt dann automatisch einen Satz von geplanten Aufgaben, mit denen das Zertifikat entschlüsselt und auf allen Front-End-Servern bereitgestellt wird.

Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Das folgende Paar von Windows PowerShell-Befehlen Ruft den Wert der Eigenschaft "Fingerabdruck" des Standardzertifikats ab und verwendet diesen Wert, um das Standardzertifikat zum Server-zu-Server-Authentifizierungszertifikat zu machen:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Im vorhergehenden Befehl ist das abgerufene Zertifikat so konfiguriert, dass es als globales Server-zu-Server-Authentifizierungszertifikat dient. Das bedeutet, dass das Zertifikat an alle Ihre Front-End-Server repliziert und von diesen verwendet wird. Dieser Befehl sollte erneut nur einmal und nur auf einem der Front-End-Server ausgeführt werden. Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das OAuthTokenIssuer-Zertifikat nicht auf jedem Front-End-Server konfigurieren. Konfigurieren Sie stattdessen das Zertifikat einmal, und lassen Sie den Replikationsserver von lync Server dafür sorgen, dass das Zertifikat auf jeden Server kopiert wird.

Das Cmdlet "festlegen-CsCertificate" übernimmt das fragliche Zertifikat und konfiguriert dieses Zertifikat sofort so, dass es als Aktuelles OAuthTokenIssuer-Zertifikat fungiert. (Lync Server 2013 speichert zwei Kopien eines Zertifikatstyps: das aktuelle Zertifikat und das vorherige Zertifikat.) Wenn Sie möchten, dass das neue Zertifikat sofort als OAuthTokenIssuer-Zertifikat fungiert, sollten Sie das Cmdlet "CsCertificate" verwenden.

Sie können auch das Cmdlet "Satz-CsCertificate" verwenden, um ein neues Zertifikat zu "Rollen". Das "Rollen" eines Zertifikats bedeutet einfach, dass Sie ein neues Zertifikat so konfigurieren, dass es zu einem bestimmten Zeitpunkt zum aktuellen OAuthTokenIssuer-Zertifikat wird. Mit diesem Befehl wird beispielsweise das Standardzertifikat abgerufen und dann dieses Zertifikat so konfiguriert, dass es vom 1. Juli 2012 als Aktuelles OAuthTokenIssuer-Zertifikat übertragen wird:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Am 1. Juli 2012 wird das neue Zertifikat als Aktuelles OAuthTokenIssuer-Zertifikat konfiguriert, und das "alte" OAuthTokenIssuer-Zertifikat wird als Vorheriges Zertifikat konfiguriert.

Wenn Sie Windows PowerShell nicht verwenden möchten, können Sie auch die MMC-Konsole Zertifikate verwenden, um ein Zertifikat von einem Front-End-Server zu exportieren und dieses Zertifikat dann auf allen anderen Front-End-Servern zu importieren. Dabei müssen Sie unbedingt den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.

<div>


> [!WARNING]
> In diesem Fall muss die Prozedur auf jedem Front-End-Server ausgeführt werden. Wenn Sie Zertifikate auf diese Weise exportieren und importieren, repliziert lync Server 2013 dieses Zertifikat nicht auf jeden Front-End-Server.



</div>

Nachdem das Zertifikat auf alle Ihre Front-End-Server importiert wurde, kann dieses Zertifikat mithilfe des lync Server-Bereitstellungs-Assistenten anstelle von Windows PowerShell zugewiesen werden. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungs-Assistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:

1.  Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server**-Bereitstellungs-Assistent.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **lync Server System installieren oder aktualisieren**.

3.  Klicken Sie auf der Microsoft lync Server 2013-Seite unter der Überschrift **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf die Schaltfläche **Ausführen** . (Hinweis: Falls Sie auf diesem Computer bereits Zertifikate installiert haben, heißt die Schaltfläche nicht **Ausführen**, sondern **Erneut ausführen**.)

4.  Wählen Sie im Zertifikat-Assistenten das Zertifikat **OAuthTokenIssuer** aus und klicken Sie auf **Zuweisen**.

5.  Klicken Sie im Zertifikatzuweisungs-Assistenten auf der Seite **Zertifikatzuweisung** auf **Weiter**.

6.  Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf der Seite für die Zusammenfassung der Zertifikatzuweisung auf **Weiter**.

8.  Klicken Sie auf der Seite „Befehle ausführen“ auf **Fertigstellen**.

9.  Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.

</div>

<span> </span>

</div>

</div>

</div>

