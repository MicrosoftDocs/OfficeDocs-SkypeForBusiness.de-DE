---
title: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d06cdb4c679d1a40eb5c6fa0e8cf837ec8d2e332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Überprüfen Sie, ob Ihre Infrastruktur die folgenden Sicherheits-, Benutzer Konfigurations-und Szenario-spezifischen Hardwarevoraussetzungen erfüllt.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Administratorrechte und Zertifikatinfrastruktur

Stellen Sie sicher, dass Ihre Umgebung mit den folgenden administrativen Benutzergruppen und der Zertifikatinfrastruktur für die Verwendung während des Enterprise-VoIP-Bereitstellungsprozesses konfiguriert ist.

  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.

  - Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
      - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
      - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
      - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.
    
    <div>
    

    > [!NOTE]
    > Mit der Delegierung können mehr Administratoren an ihrer lync Server-Bereitstellung teilnehmen, ohne unnötigen Zugriff auf Ressourcen zu öffnen.

    
    </div>

  - Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.
    
    <div>
    

    > [!NOTE]
    > Details zu den Zertifikatanforderungen in lync Server finden Sie unter <A href="lync-server-2013-certificate-infrastructure-requirements.md">Zertifikatsinfrastruktur Anforderungen für lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Benutzerkonfiguration

Wenn Sie den Vermittlungsserver mit jedem Front-End-Pool oder Standard Edition-Server während der Front-End-Bereitstellung zusammengestellt haben, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Server Rollen automatisch konfiguriert.

Wenn Sie die Enterprise-VoIP-Arbeitsauslastung zu diesem Zeitpunkt neu bereitstellen, bevor Sie mit dem Bereitstellungsprozess beginnen, legen Sie für jeden Benutzer, den Sie für Enterprise-VoIP aktivieren möchten, eine primäre Telefonnummer fest. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung müssen alle primären Telefonnummern normalisiert (korrekt formatiert) und mithilfe der lync Server-Systemsteuerung in die Eigenschaft des jeweiligen Benutzer- **URI** kopiert werden.

<div>


> [!NOTE]
> Beispiele für primäre Telefonnummern, die für die Bereitstellung von Enterprise-VoIP erforderlich sind, finden Sie im Abschnitt " <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln" 2013 im</A> Abschnitt " <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Wählpläne und Normalisierungsregeln</A> " in lync Server 2013 in der Planning-Dokumentation.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Konnektivität

Nachdem Sie die Voraussetzungen für Software und Umwelt für Enterprise-VoIP überprüft haben, können Sie die folgenden Inhalte für folgende Zwecke verwenden:

  - Installieren Sie den Vermittlungsserver, wie unter [Installieren der Dateien für den Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder Pool bereitstellen möchten, weil Vermittlungsserver als Teil des Front-End-Pools oder Standard installiert werden. Edition Server-Bereitstellungsprozess, wenn er sich befindet.

  - Oder beginnen Sie mit der Konfiguration von Einstellungen für die Weiterleitung von Anrufen für Enterprise-VoIP-Benutzer, wie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

