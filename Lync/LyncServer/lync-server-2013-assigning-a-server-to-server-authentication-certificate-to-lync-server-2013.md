---
title: Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Microsoft Lync Server 2013
TOCTitle: Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205253(v=OCS.15)
ms:contentKeyID: 49295364
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen eines Zertifikats für die Server-zu-Server-Authentifizierung zu Microsoft Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-24_

Führen Sie in der Verwaltungsshell für Lync Server 2013 den folgenden Befehl aus, um zu bestimmen, ob ein Server-zu-Server-Authentifizierungszertifikat bereits Microsoft Lync Server 2013 zugewiesen wurde:

    Get-CsCertificate -Type OAuthTokenIssuer

Falls keine Zertifikatsinformationen zurückgegeben werden, müssen Sie ein Zertifikat des Tokenausstellers zuweisen, damit Sie die Server-zu-Server-Authentifizierung verwenden können. Als Faustregel gilt, dass Sie jedes Lync Server 2013-Zertifikat als OAuthTokenIssuer-Zertifikat verwenden können. Beispielsweise kann Ihr Lync Server 2013-Standardzertifikat auch als OAuthTokenIssuer-Zertifikat verwendet werden. (Beim OAUthTokenIssuer-Zertifikat kann es sich auch um irgendein Webserverzertifikat handeln, das den Namen Ihrer SIP-Domäne im Feld Thema enthält.) Dies sind die beiden wichtigsten Anforderungen für das für die Server-zu-Server-Authentifizierung verwendete Zertifikat: 1) Dasselbe Zertifikat muss als OAuthTokenIssuer-Zertifikat auf allen Ihren Front-End-Servern konfiguriert sein; und 2) das Zertifikat muss mindestens eine Länge von 2048 Bits aufweisen.

Wenn Sie nicht über ein Zertifikat verfügen, das für die Server-zu-Server-Authentifizierung verwendet werden kann, können Sie ein neues Zertifikat beziehen, das neue Zertifikat importieren und anschließend dieses Zertifikat für die Server-zu-Server-Authentifizierung verwenden. Nachdem Sie das neue Zertifikat angefordert und bezogen haben, können Sie sich an jedem Ihrer Front-End-Server anmelden und mit einem Windows PowerShell-Befehl, der so oder ähnlich aussieht, dieses Zertifikat importieren und zuweisen:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

Im vorherigen Befehl stellt der Path-Parameter den vollständigen Pfad zur Zertifikatdatei dar, und der Password-Parameter stellt das Kennwort dar, das dem Zertifikat zugewiesen wurde. Dieses Verfahren sollte nur einmal ausgeführt werden. Der Lync Server-Replikationsdienst erstellt dann automatisch geplante Vorgänge, mit denen das Zertifikat für alle Ihre Front-End-Server entschlüsselt und bereitgestellt wird.

Alternativ können Sie ein vorhandenes Zertifikat als Server-zu-Server-Authentifizierungszertifikat verwenden. (Das Standardzertifikat kann wie bereits erwähnt als Server-zu-Server-Authentifizierungszertifikat verwendet werden.) Mit dem folgenden Windows PowerShell-Befehlspaar wird der Wert der Thumbprint-Eigenschaft des Standardzertifikats abgerufen. Anschließend wird unter Verwendung dieses Werts das Standardzertifikat als Server-zu-Server-Authentifizierungszertifikat festgelegt:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

Im vorherigen Befehl wird das abgerufene Zertifikat als globales Server-zu-Server-Authentifizierungszertifikat konfiguriert. Dies bedeutet, dass das Zertifikat für alle Ihre Front-End-Server repliziert und von diesen verwendet wird. Dieser Befehl sollte wiederum nur einmal ausgeführt werden, und nur auf einem Ihrer Front-End-Server. Alle Front-End-Server müssen zwar dasselbe Zertifikat verwenden, aber Sie sollten das OAuthTokenIssuer-Zertifikat nicht auf jedem Front-End-Server konfigurieren. Konfigurieren Sie stattdessen das Zertifikat einmal, und überlassen Sie dann dem Lync Server-Replikationsdienst das Kopieren dieses Zertifikats auf jeden Server.

Mit dem Set-CsCertificate-Cmdlet wird das betreffende Zertifikat sofort als aktuelles OAuthTokenIssuer-Zertifikat konfiguriert. (Lync Server 2013 verwaltet zwei Kopien eines Zertifikattyps, nämlich das aktuelle Zertifikat und das vorherige Zertifikat.) Falls Sie das neue Zertifikat sofort als OAuthTokenIssuer-Zertifikat verwenden müssen, sollten Sie das Set-CsCertificate-Cmdlet verwenden.

Mit dem Set-CsCertificate-Cmdlet können Sie auch ein neues Zertifikat "rollen". Das "Rollen" eines Zertifikats bedeutet einfach, dass Sie festlegen, dass ein neues Zertifikat ab einem bestimmten Zeitpunkt das aktuelle OAuthTokenIssuer-Zertifikat wird. Beispielsweise wird mit dem folgenden Befehl das Standardzertifikat abgerufen und dann dieses Zertifikat ab dem 1. Juli 2012 als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Am 1. Juli 2012 wird das neue Zertifikat als das aktuelle OAuthTokenIssuer-Zertifikat konfiguriert, und das "alte" OAuthTokenIssuer-Zertifikat wird als vorheriges Zertifikat konfiguriert.

Falls Sie Windows PowerShell nicht verwenden möchten, können Sie auch mithilfe der MMC-Konsole "Zertifikate" ein Zertifikat von einem Front-End-Server exportieren und anschließend dieses Zertifikat auf allen Ihren anderen Front-End-Servern importieren. Dabei müssen Sie unbedingt den privaten Schlüssel zusammen mit dem Zertifikat selbst exportieren.

> [!CAUTION]  
> In diesem Fall muss das Verfahren auf jedem Front-End-Server ausgeführt werden. Beim Exportieren und Importieren von Zertifikaten auf diese Weise repliziert Lync Server 2013 dieses Zertifikat nicht auf jedem Front-End-Server.


Nachdem das Zertifikat auf allen Ihren Front-End-Servern importiert wurde, kann es dann anstatt mit Windows PowerShell mithilfe des Lync Server-Bereitstellungs-Assistenten zugewiesen werden. Führen Sie zum Zuweisen eines Zertifikats mithilfe des Bereitstellungs-Assistenten die folgenden Schritte auf einem Computer aus, auf dem der Bereitstellungs-Assistent installiert wurde:

1.  Klicken Sie auf Start, auf Alle Programme, auf **Microsoft Lync Server 2013** und dann auf **Lync Server-Bereitstellungs-Assistent**.

2.  Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.

3.  Klicken Sie auf der Seite Microsoft Lync Server 2013 auf die Schaltfläche **Ausführen** im Abschnitt **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**. (Hinweis: Falls Sie auf diesem Computer bereits Zertifikate installiert haben, heißt die Schaltfläche **Ausführen** stattdessen **Erneut ausführen**.)

4.  Wählen Sie im Zertifikat-Assistenten das Zertifikat **OAuthTokenIssuer** aus, und klicken Sie auf **Zuweisen**.

5.  Klicken Sie im Zertifikatzuweisungs-Assistenten auf der Seite **Zertifikatzuweisung** auf **Weiter**.

6.  Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das für die Server-zu-Server-Authentifizierung verwendet werden soll, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie auf der Seite Zusammenfassung der Zertifikatzuweisung auf **Weiter**.

8.  Klicken Sie auf der Seite Befehle werden ausgeführt auf **Fertig stellen**.

9.  Schließen Sie den Zertifikat-Assistenten und den Bereitstellungs-Assistenten.

