---
title: 'Lync Server 2013: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP'
TOCTitle: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398221(v=OCS.15)
ms:contentKeyID: 49293273
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Stellen Sie sicher, dass Ihre Infrastruktur die folgenden Anforderungen an Sicherheit, Benutzerkonfiguration und die szenariospezifische Hardware erfüllt.

## Administrative Rechte und Zertifikatinfrastruktur

Stellen Sie sicher, dass Ihre Umgebung für die Enterprise-VoIP-Bereitstellung mit den folgenden administrativen Benutzergruppen und der angegebenen Zertifikatinfrastruktur konfiguriert ist.

  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

  - Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
      - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
      - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem Richtlinien auf Benutzerebene zuweisen. Hiervon ausgenommen ist die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
      - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator" und "CsUserAdministrator" ausgeführt werden können.
    

    > [!NOTE]
    > Die Delegierung ermöglicht es, dass mehrere Administratoren an Ihrer Lync Server-Bereitstellung arbeiten, ohne dass unnötig Zugriff auf Ressourcen gewährt wird.



  - Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.
    

    > [!NOTE]
    > Ausführliche Informationen zu Zertifikatanforderungen in Lync Server finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-certificate-infrastructure-requirements.md">Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013</A> .



## Benutzerkonfiguration

Wenn Sie den Vermittlungsserver bei der Front-End-Bereitstellung gemeinsam mit jedem Front-End-Pool oder Standard Edition-Server ausführen, wurden die erforderlichen Benutzereinstellungen für Enterprise-VoIP während der Installation der Dateien für diese Serverrollen automatisch konfiguriert.

Wenn Sie Enterprise-VoIP neu bereitstellen, müssen Sie vor Beginn der Bereitstellung eine primäre Rufnummer für jeden Benutzer bereitstellen, der für Enterprise-VoIP aktiviert werden soll. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung müssen alle primären Rufnummern normalisiert (richtig formatiert) und unter Verwendung der Lync Server-Systemsteuerung in die Eigenschaft **Anschluss-URI** für jeden Benutzer kopiert werden.


> [!NOTE]
> Beispiele für primäre Rufnummern, die für eine Enterprise-VoIP-Bereitstellung erforderlich sind, finden Sie im Abschnitt <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln in Lync Server 2013</A> von <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln in Lync Server 2013</A> in der Planungsdokumentation.



## Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung

Nachdem Sie überprüft haben, dass die Software- und Umgebungsanforderungen für Enterprise-VoIP erfüllt sind, können Sie die folgenden Schritte ausführen:

  - Installieren Sie den Vermittlungsserver, wie beschrieben unter [Installieren der Dateien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md). Dies gilt nur, wenn Sie einen eigenständigen Vermittlungsserver oder -pool bereitstellen möchten, da Vermittlungsserver bei gemeinsamer Ausführung im Rahmen der Front-End-Pool- oder Standard Edition-Server-Bereitstellung installiert werden.

  - Oder: Konfigurieren Sie die Einstellungen für das Anrufrouting für Enterprise-VoIP-Benutzer, wie beschrieben unter [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).

