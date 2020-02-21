---
title: Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8aec487e2ef5c6f5a756305a6e44df0c31cbec0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Stellen Sie sicher, dass Ihre Infrastruktur die folgenden Anforderungen an Sicherheit, Benutzerkonfiguration und die szenariospezifische Hardware erfüllt.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>Administrative Rechte und Zertifikatinfrastruktur

Stellen Sie sicher, dass Ihre Umgebung für die Enterprise-VoIP-Bereitstellung mit den folgenden administrativen Benutzergruppen und der angegebenen Zertifikatinfrastruktur konfiguriert ist.

  - Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe "RTCUniversalServerAdmins" sein.

  - Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
      - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
      - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem Richtlinien auf Benutzerebene zuweisen. Hiervon ausgenommen ist die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
      - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator" und "CsUserAdministrator" ausgeführt werden können.
    
    <div>
    

    > [!NOTE]
    > Die Delegierung ermöglicht es mehr Administratoren, an ihrer lync Server-Bereitstellung teilzunehmen, ohne unnötigen Zugriff auf Ressourcen zu öffnen.

    
    </div>

  - Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.
    
    <div>
    

    > [!NOTE]
    > Ausführliche Informationen zu den Zertifikatanforderungen in lync Server finden Sie unter <A href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate Infrastructure Requirements for lync Server 2013</A> in der Planungsdokumentation.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>Benutzerkonfiguration

Wenn Sie die Vermittlungsserver bei der Front-End-Bereitstellung mit jedem Front-End-Pool oder Standard Edition-Server zusammengestellt haben, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Server Rollen automatisch konfiguriert.

Wenn Sie Enterprise-VoIP neu bereitstellen, müssen Sie vor Beginn der Bereitstellung eine primäre Rufnummer für jeden Benutzer bereitstellen, der für Enterprise-VoIP aktiviert werden soll. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung müssen alle primären Telefonnummern normalisiert (ordnungsgemäß formatiert) und in die **URI** -Eigenschaft jedes Benutzers mit lync Server-Systemsteuerung kopiert werden.

<div>


> [!NOTE]
> Beispiele für primäre Telefonnummern, die für die Bereitstellung von Enterprise-VoIP erforderlich sind, finden Sie in der Planungsdokumentation unter <A href="lync-server-2013-dial-plans-and-normalization-rules.md">lync Server 2013</A> Abschnitt Wähl <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Einstellungen und Normalisierungsregeln in lync Server 2013</A> .



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung

Nachdem Sie überprüft haben, dass die Software- und Umgebungsanforderungen für Enterprise-VoIP erfüllt sind, können Sie die folgenden Schritte ausführen:

  - Installieren Sie die Vermittlungsserver, wie in [Installieren der Dateien für Vermittlungsserver in lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)beschrieben, jedoch nur, wenn Sie eine eigenständige Vermittlungsserver oder einen Pool bereitstellen möchten, da Vermittlungsserver im Rahmen des Front-End-Pool-oder Standard Edition-Server Bereitstellungsprozesses installiert werden.

  - Oder beginnen Sie mit der Konfiguration von Einstellungen für die Weiterleitung von Anrufen für Enterprise-VoIP-Benutzer, wie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md)beschrieben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

