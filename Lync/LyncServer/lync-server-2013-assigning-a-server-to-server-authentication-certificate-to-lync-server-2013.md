---
title: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu lync Server 2013
description: Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 042158167f89dc2b6e743e8db94149d4f1cbc1a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560541"
---
# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Zuweisen eines Server-zu-Server-Authentifizierungszertifikats zu Microsoft lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-24_

Um zu ermitteln, ob Microsoft lync Server 2013 bereits ein Server-zu-Server-Authentifizierungszertifikat zugewiesen wurde, führen Sie den folgenden Befehl in der lync Server 2013-Verwaltungsshell aus:

    Get-CsCertificate -Type OAuthTokenIssuer

Wenn keine Zertifikatinformationen zurückgegeben werden, müssen Sie ein Token-Ausstellerzertifikat zuweisen, bevor Sie die Server-zu-Server-Authentifizierung verwenden können. Allgemein gilt, dass lync Server 2013 Zertifikat als OAuthTokenIssuer-Zertifikat verwendet werden kann. Beispielsweise kann das lync Server 2013 Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Das OAUthTokenIssuer-Zertifikat kann auch ein beliebiges Webserverzertifikat sein, das den Namen der SIP-Domäne im Feld Betreff enthält.) Die primären zwei Anforderungen für das Zertifikat, das für die Server-zu-Server-Authentifizierung verwendet wird, sind folgende: 1) das gleiche Zertifikat muss als OAuthTokenIssuer-Zertifikat auf allen Front-End-Servern konfiguriert sein. und, 2) das Zertifikat muss mindestens 2048 Bits sein.

Wenn Sie nicht über ein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat erhalten, das neue Zertifikat importieren und dann dieses Zertifikat für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und erhalten haben, können Sie sich dann bei einem beliebigen Front-End-Server anmelden und einen Windows PowerShell-Befehl wie den folgenden verwenden, um dieses Zertifikat zu importieren und zuzuweisen:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Im vorherigen Befehl stellt der Parameter path den vollständigen Pfad zur Zertifikatsdatei dar, und der Parameter Password stellt das Kennwort dar, das dem Zertifikat zugewiesen wurde. Dieses Verfahren sollte nur einmal ausgeführt werden: der Replikationsdienst von lync Server erstellt dann automatisch eine Reihe geplanter Aufgaben, mit denen das Zertifikat auf allen Front-End-Servern entschlüsselt und bereitgestellt wird.

Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Wie bereits erwähnt, kann das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Das folgende paar Windows PowerShell Befehle Ruft den Wert der Eigenschaft "Fingerabdruck" des Standardzertifikats ab und verwendet diesen Wert, um das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat festzustellen:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Im vorherigen Befehl ist das abgerufene Zertifikat für die Funktion als globales Server-zu-Server-Authentifizierungszertifikat konfiguriert. Das bedeutet, dass das Zertifikat auf allen Front-End-Servern repliziert und von diesen verwendet wird. Dieser Befehl sollte wiederum nur einmal und nur auf einem Ihrer Front-End-Server ausgeführt werden. Obwohl alle Front-End-Server dasselbe Zertifikat verwenden müssen, sollten Sie das OAuthTokenIssuer-Zertifikat nicht auf jeder Front-End-Server konfigurieren. Konfigurieren Sie das Zertifikat stattdessen einmal, und überlassen Sie es dem Replikations Server von lync Server, dieses Zertifikat auf jeden Server zu kopieren.

Das Set-CsCertificate-Cmdlet übernimmt das betreffende Zertifikat und konfiguriert dieses Zertifikat sofort als Aktuelles OAuthTokenIssuer-Zertifikat. (Lync Server 2013 zwei Kopien eines Zertifikattyps aufbewahrt: das aktuelle Zertifikat und das vorherige Zertifikat.) Wenn das neue Zertifikat sofort als OAuthTokenIssuer-Zertifikat fungieren soll, sollten Sie das Set-CsCertificate-Cmdlet verwenden.

Sie können auch das Cmdlet Set-CsCertificate verwenden, um ein neues Zertifikat zu "Rollen". "Rolling" ein Zertifikat bedeutet einfach, dass Sie ein neues Zertifikat zu einem bestimmten Zeitpunkt als Aktuelles OAuthTokenIssuer-Zertifikat konfigurieren. Dieser Befehl ruft beispielsweise das Standardzertifikat ab und konfiguriert dann das Zertifikat für die Übernahme als Aktuelles OAuthTokenIssuer-Zertifikat vom 1. Juli 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Am 1. Juli 2012 wird das neue Zertifikat als Aktuelles OAuthTokenIssuer-Zertifikat konfiguriert, und das alte OAuthTokenIssuer-Zertifikat wird als das vorherige Zertifikat konfiguriert.

Wenn Sie Windows PowerShell nicht verwenden möchten, können Sie auch die MMC-Konsole Zertifikate verwenden, um ein Zertifikat aus einem Front-End-Server zu exportieren und dieses Zertifikat dann auf allen anderen Front-End-Servern zu importieren. Wenn Sie dies tun, stellen Sie sicher, dass Sie den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.

<div>


> [!WARNING]
> In diesem Fall muss die Prozedur für jede Front-End-Server ausgeführt werden. Beim Exportieren und Importieren von Zertifikaten auf diese Weise werden lync Server 2013 dieses Zertifikat nicht für jeden Front-End-Server repliziert.



</div>

Nachdem das Zertifikat auf alle Front-End-Server importiert wurde, kann dieses Zertifikat mithilfe des lync Server-Bereitstellungs-Assistenten anstelle von Windows PowerShell zugewiesen werden. Wenn Sie ein Zertifikat mithilfe des Bereitstellungs-Assistenten zuweisen möchten, führen Sie die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:

1.  Klicken Sie im Startmenü auf alle Programme, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

3.  Klicken Sie auf der Seite Microsoft lync Server 2013 unter der Überschrift **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**auf die Schaltfläche **Ausführen** . (Hinweis: Wenn Sie bereits Zertifikate auf diesem Computer installiert haben, wird die Schaltfläche **Ausführen** erneut mit der Bezeichnung **Run**versehen.)

4.  Wählen Sie im Zertifikat-Assistenten das **OAuthTokenIssuer** -Zertifikat aus, und klicken Sie dann auf **zuweisen**.

5.  Klicken Sie im Assistenten für die zertifikatzuweisung auf der Seite **zertifikatzuweisung** auf **weiter**.

6.  Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll, und klicken Sie dann auf **weiter**.

7.  Klicken Sie auf der Seite Zusammenfassung der Zertifikatzuweisung auf **Weiter**.

8.  Klicken Sie auf der Seite Befehle ausführen auf **Fertig stellen**.

9.  Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.

</div>

<span> </span>

</div>

</div>

</div>

