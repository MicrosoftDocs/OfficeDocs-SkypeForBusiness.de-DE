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
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Konfigurieren von Zertifikaten für Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-17_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein, oder an Sie müssen geeignete Berechtigungen delegiert worden sein. Ausführliche Informationen zum Delegieren von Berechtigungen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md). In Abhängigkeit von Ihrer Organisation und den Anforderungen zum Anfordern von Zertifikaten sind möglicherweise weitere Gruppenmitgliedschaften erforderlich. Wenden Sie sich an die Gruppe, die Ihre Public Key-Infrastruktur-Zertifizierungsstelle verwaltet.

<div>


> [!NOTE]  
> Lync Server 2013 enthält Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digest-Längen von 224, 256, 384 oder 512 Bits) von Digest-Hash-und Signaturalgorithmen für Verbindungen von Clients, auf denen die Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista oder Windows XP-Betriebssysteme, zusätzlich zu lync Phone Edition. Um den externen Zugriff mithilfe der SHA-2-Suite zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit demselben Bit-Längen-Digest ausgeben kann.



</div>

<div>


> [!WARNING]  
> Die Auswahl des Hash Digest-und Signaturalgorithmus hängt von den Clients und den Servern ab, auf denen das Zertifikat verwendet wird, sowie von anderen Computern und Geräten, mit denen Clients und Server kommunizieren, die auch wissen müssen, wie die in der Anwendung verwendeten Algorithmen verwendet werden sollen. Zertifikat. Informationen darüber, welche Digest-Längen im Betriebssystem und in einigen Clientanwendungen unterstützt<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>werden, finden Sie unter.



</div>

Jede Standard Edition-Server oder Front-End-Server erfordert bis zu vier Zertifikate: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein webinternes Zertifikat und ein webbasiertes externes Zertifikat. Es ist jedoch möglich, ein einzelnes Standardzertifikat mit entsprechenden Einträgen für alternative Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anzufordern und zuzuweisen. Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für interne Server in lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Ausführliche Informationen zum anfordern, zuweisen und Installieren des oAuthTokenIssuer-Zertifikats finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)

Verwenden Sie das folgende Verfahren, um die Standard Edition-Server-oder Front-End-Server Zertifikate anzufordern, zuzuweisen und zu installieren. Wiederholen Sie das Verfahren für jede Front-End-Server.

<div>


> [!IMPORTANT]  
> Im folgenden Verfahren wird beschrieben, wie Sie Zertifikate von einer internen Unternehmens PKI, die von Ihrer Organisation bereitgestellt wird, und bei der Offline Anforderungsverarbeitung konfigurieren. Informationen zum Abrufen von Zertifikaten von einer öffentlichen Zertifizierungsstelle finden Sie unter <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Zertifikatanforderungen für interne Server in lync Server 2013</A> in der Planungsdokumentation. In diesem Verfahren wird außerdem beschrieben, wie Sie Zertifikate während der Einrichtung des Front-End-Server anfordern, zuweisen und installieren. Wenn Sie Zertifikate im Voraus angefordert haben, wie im Abschnitt <A href="lync-server-2013-request-certificates-in-advance-optional.md">Anforderungs Zertifikate im Voraus (optional) für lync Server 2013</A> Abschnitt dieser Bereitstellungsdokumentation beschrieben, oder wenn Sie keine interne Enterprise-PKI in Ihrer Organisation bereitgestellt haben, um Zertifikate zu erhalten, müssen Sie dieses Verfahren nach Bedarf ändern.



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>So konfigurieren Sie Zertifikate für einen Front-End-Server

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf **Ausführen** neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**.

2.  Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter**.

4.  Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.

5.  Wählen Sie auf der Seite Zertifizierungs **Stelle** auswählen in der Liste **in Ihrer Umgebung erkannte Liste eine Zertifizierungsstelle auswählen aus** , und wählen Sie dann eine bekannte Zertifizierungsstelle (über die Registrierung in Active Directory-Domänendienste) aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.

6.  Auf der Seite **Zertifizierungsstellenkonto** werden Sie zur Angabe von Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatanforderung bei der Zertifizierungsstelle aufgefordert. Sie müssen vorab festlegen, ob ein Benutzername und Kennwort zum Anfordern eines Zertifikats erforderlich ist. Der Zertifizierungsstellenadministrator verfügt über die benötigten Informationen und kann Ihnen ggf. bei diesem Schritt helfen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben einen Benutzernamen und ein Kennwort in die Textfelder ein und klicken dann auf **Weiter**.

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    <div>
    

    > [!NOTE]  
    > Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben.

    
    </div>

8.  Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen Wert für **Anzeigename** ein, anhand dessen das Zertifikat und sein Zweck bestimmt werden. Falls leer gelassen, wird ein Name automatisch generiert. Geben Sie in **Bitlänge** die Bitlänge des Schlüssels ein, oder übernehmen Sie den Standardwert von 2048 Bits. Durch Auswahl der Option **Privaten Schlüssel des Zertifikats als exportierbar markieren** können Sie bei Bedarf das Zertifikat und den privaten Schlüssel in andere Systeme verschieben oder kopieren. Klicken Sie anschließend auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 hat minimale Anforderungen an einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet.

    
    </div>

9.  Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter**.

10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter**.

11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.

12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne**, und klicken Sie dann auf **Weiter**.

13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.

14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.

15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.

16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn das Zertifikat als ausgestellt und installiert gemeldet wird, jedoch nicht gültig ist, stellen Sie sicher, dass das Zertifizierungsstellen-Stammzertifikat im vertrauenswürdigen Stammzertifizierungsstellen-Speicher des Servers installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Das Kontrollkästchen **Dieses Zertifikat Lync Server-Zertifikatsverwendungen zuweisen** ist standardmäßig aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.

17. Wenn das Kontrollkästchen **Dieses Zertifikat Lync Server-Zertifikatsverwendungen zuweisen** auf der vorherigen Seite deaktiviert wurde, wird die Seite **Zertifikatzuweisung** angezeigt. Klicken Sie auf **Weiter**.

18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn auf der Seite <STRONG>Status der Onlinezertifikatsanforderung</STRONG> ein Problem mit dem Zertifikat gemeldet wird (wenn das Zertifikat beispielsweise als ungültig angezeigt wird), kann das Anzeigen des tatsächlichen Zertifikats bei der Lösung des Problems helfen. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.

    
    </div>

19. Überprüfen Sie auf der Seite **Zusammenfassung der zertifikatzuweisung** die angezeigten Informationen, um sicherzustellen, dass es sich um das Zertifikat handelt, das zugewiesen werden soll, und klicken Sie dann auf **weiter**.

20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.

21. Überprüfen Sie auf der Seite **Zertifikat-Assistent** , ob der **Status** des Zertifikats "zugewiesen" ist, und klicken Sie dann auf **Schließen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Anforderungen an die Zertifikatinfrastruktur für lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

