---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 303724fa705fa94e9bbacacb4764bba7b918c460
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-17_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über die richtigen Berechtigungen delegiert wurde. Details zum Delegieren von Berechtigungen finden Sie unter Berechtigungen für das [Delegieren von Setup in lync Server 2013](lync-server-2013-delegate-setup-permissions.md). Je nach Organisation und Anforderungen für das Anfordern von Zertifikaten müssen Sie möglicherweise weitere Gruppenmitgliedschaften anfordern. Konsultieren Sie die Gruppe, die Ihre PKI-Zertifizierungsstelle (Public Key Infrastructure) verwaltet.

<div>


> [!NOTE]  
> Lync Server 2013 enthält Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digest-Längen von 224, 256, 384 oder 512-Bits) von Digest-Hash-und-Signaturalgorithmen für Verbindungen von Clients, auf denen Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista oder Windows XP-Betriebssysteme, zusätzlich zu lync Phone Edition. Damit der externe Zugriff über die SHA-2-Suite unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit einem Digest gleicher Bitlänge ausstellen kann.



</div>

<div>


> [!WARNING]  
> Die Auswahl des verwendeten Hashdigests und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden sollen, sowie von den anderen Computern und Geräten, mit denen Clients und Server kommunizieren sollen, die ebenfalls imstande sein müssen, die im Zertifikat enthaltenen Algorithmen zu verwenden. Informationen dazu, welche Digest-Längen im Betriebssystem und einigen Clientanwendungen unterstützt werden<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>, finden Sie unter.



</div>

Für jeden Standard Edition-Server oder Front-End-Server sind bis zu vier Zertifikate erforderlich: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein webinternes Zertifikat und ein externes Webzertifikat. Es ist jedoch möglich, ein einzelnes Standardzertifikat mit den entsprechenden Einträgen für den alternativen Subjektnamen sowie das oAuthTokenIssuer-Zertifikat anzufordern und zuzuweisen. Details zu den Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Details zum anfordern, zuweisen und Installieren des oAuthTokenIssuer-Zertifikats finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Gehen Sie wie folgt vor, um die Standard Edition-Server-oder Front-End-Serverzertifikate anzufordern, zuzuweisen und zu installieren. Wiederholen Sie den Vorgang für jeden Front-End-Server.

<div>


> [!IMPORTANT]  
> Im folgenden Verfahren wird beschrieben, wie Sie Zertifikate aus einer internen Unternehmens PKI, die von Ihrer Organisation bereitgestellt wird, und mit der Offline Anforderungsverarbeitung konfigurieren. Informationen zum Abrufen von Zertifikaten von einer öffentlichen Zertifizierungsstelle finden Sie unter <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Zertifikatanforderungen für interne Server in lync Server 2013</A> in der Planungsdokumentation. In diesem Verfahren wird auch beschrieben, wie Sie während der Einrichtung des Front-End-Servers Zertifikate anfordern, zuweisen und installieren. Wenn Sie Zertifikate im Voraus angefordert haben, wie im Abschnitt <A href="lync-server-2013-request-certificates-in-advance-optional.md">anfordern von Zertifikaten im Voraus (optional) für lync Server 2013</A> dieser Bereitstellungsdokumentation beschrieben wird, oder wenn Sie keine interne, in Ihrer Organisation bereitgestellte Unternehmens PKI verwenden, um Zertifikate zu erhalten, müssen Sie dieses Verfahren nach Bedarf ändern.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>So konfigurieren Sie Zertifikate für einen Front-End-Server

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen** .

2.  Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **weiter**.

4.  Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Bei Auswahl dieser Option muss die interne Zertifizierungsstelle mit automatischer Onlineregistrierung verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Anschließend müssen Sie die Zertifikatantwort importieren und der entsprechenden Zertifikatrolle zuweisen.

5.  Wählen Sie auf der Seite Zertifizierungs **Stelle auswählen** die Option **eine Zertifizierungsstelle in der Liste in Ihrer Umgebung gefunden** auswählen aus, und wählen Sie dann in der Liste eine bekannte Zertifizierungsstelle (durch Registrierung in Active Directory-Domänendienste) aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.

6.  Auf der Seite **Certificate Authority-Konto** werden Sie zur Eingabe der Anmeldeinformationen aufgefordert, um die Zertifikatanforderung bei der Zertifizierungsstelle anzufordern und zu verarbeiten. Sie sollten festgestellt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um ein Zertifikat im Voraus anzufordern. Ihr Zertifizierungsstellenadministrator verfügt über die erforderlichen Informationen und kann Sie in diesem Schritt unterstützen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie in den Textfeldern einen Benutzernamen und ein Kennwort ein, und klicken Sie dann auf **weiter**.

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    <div>
    

    > [!NOTE]  
    > Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben.

    
    </div>

8.  Geben Sie auf der Seite **Name und Sicherheitseinstellungen** einen **Anzeigenamen** an, der es Ihnen ermöglichen soll, das Zertifikat und den Zweck zu identifizieren. Wenn Sie das Feld leer lassen, wird automatisch ein Name generiert. Stellen Sie die **Bit-Länge** des Schlüssels ein, oder übernehmen Sie den Standardwert von 2048-Bits. Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aus, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel verschoben oder auf andere Systeme kopiert werden müssen, und klicken Sie dann auf **weiter**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 verfügt über minimale Anforderungen für einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet.

    
    </div>

9.  Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an und klicken Sie dann auf **Weiter**.

10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an und klicken Sie dann auf **Weiter**.

11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.

12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne** und klicken Sie dann auf **Weiter**.

13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an und klicken Sie auf **Weiter**.

14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.

15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.

16. Überprüfen Sie auf der Seite **Status der Online Zertifikatanforderung** die zurückgegebenen Informationen. Beachten Sie, dass das Zertifikat ausgestellt und im lokalen Zertifikatspeicher installiert wurde. Wenn Sie als ausgestellt und installiert, aber ungültig gemeldet wird, stellen Sie sicher, dass das Zertifizierungsstellen-Stammzertifikat im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Servers installiert wurde. Informationen zum Abrufen eines vertrauenswürdigen Stammzertifizierungsstellen-Zertifikats finden Sie in ihrer Zertifizierungsstellen-Dokumentation. Wenn Sie das abgerufene Zertifikat anzeigen müssen, klicken Sie auf **Zertifikat Details anzeigen**. Standardmäßig ist das Kontrollkästchen für **die Verwendung des Zertifikats für lync Server-Zertifikate zuweisen** aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.

17. Wenn Sie das Kontrollkästchen für **das Zuweisen des Zertifikats zu lync Server-Zertifikat Verwendungen** auf der vorherigen Seite deaktiviert haben, wird die Seite **zertifikatzuweisung** angezeigt. Click **Next**.

18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn auf der Status Seite der <STRONG>Online Zertifikatanforderung</STRONG> ein Problem mit dem Zertifikat gemeldet wurde, beispielsweise wenn das Zertifikat nicht gültig ist, kann die Anzeige des tatsächlichen Zertifikats bei der Lösung des Problems behilflich sein. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.

    
    </div>

19. Überprüfen Sie anhand der Informationen auf der Seite **Zusammenfassung der Zertifikatzuweisung**, dass es sich um das zuzuweisende Zertifikat handelt, und klicken Sie dann auf **Weiter**.

20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.

21. Überprüfen Sie auf der Seite des **Zertifikat-Assistenten** , ob der **Status** des Zertifikats "zugewiesen" lautet, und klicken Sie dann auf **Schließen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

