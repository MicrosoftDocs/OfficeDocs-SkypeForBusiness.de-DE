---
title: Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b1dd5fd119022807fbc64218c80e24a33557aa1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition Geräten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Obwohl Quality of Service (QoS) für Geräte wie iPhones standardmäßig nicht aktiviert ist, ist QoS standardmäßig für Geräte aktiviert, auf denen lync Phone Edition ausführt. (Diese Geräte werden gemeinhin als UC-oder Unified Communication-Telefone bezeichnet.) Um dies zu überprüfen, führen Sie den folgenden Windows PowerShell Befehl in der lync Server-Verwaltungsshell aus:

    Get-CsUCPhoneConfiguration

Wenn Sie keine Änderungen an Ihren UC-Telefon Konfigurationseinstellungen vorgenommen haben, erhalten Sie wieder Informationen, die wie folgt aussehen:

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

Für Dienst Qualitäts Zwecke ist nur eine dieser Eigenschaften von Interesse: VoiceDiffServTag. VoiceDiffServTag stellt den DSCP-Wert dar, der dem VoIP-Datenverkehr zugewiesen ist, der von einem lync-Phone Edition Gerät stammt.

<div>


> [!NOTE]
> Der Parameter Voice8021p wird in lync Server 2013 nicht mehr unterstützt. Der-Parameter ist weiterhin gültig aus Gründen der Abwärtskompatibilität mit Microsoft lync Server 2010; Sie hat jedoch keine Auswirkung auf Geräte, die mit lync Server 2013 verwendet werden.



</div>

In den meisten Netzwerken sollte das Markieren von lync Phone Edition-Paketen mit einer VoiceDiffServTag von 40 keine Probleme verursachen. 40 ist jedoch nicht der in der Regel für den Audioverkehr verwendete Wert; Stattdessen wird der Audioverkehr fast immer mit dem DSCP-Code 46 markiert. Um die Konsistenz im gesamten Netzwerk aufrechtzuerhalten, können Sie die VoiceDiffServTag-Eigenschaft Ihrer UC-Telefone auf 46 ändern.

Dazu können Sie entweder Windows PowerShell oder den lync Server-Systemsteuerung verwenden. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um den VoiceDiffServTag-Wert mithilfe von Windows PowerShell zu ändern:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Der obige Befehl ändert die globale Sammlung von UC-Telefon Konfigurationseinstellungen. Beachten Sie jedoch, dass UC-Telefoneinstellungen auch dem Standortbereich zugewiesen werden können. Um UC-Telefon Konfigurationseinstellungen auf Standortebene zu ändern, müssen Sie die Websiteidentität angeben. Beispiel:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Sie können auch den folgenden Befehl verwenden, um alle Konfigurationseinstellungen für UC-Telefone gleichzeitig zu ändern:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Wenn Sie diese Änderung lieber mit lync Server-Systemsteuerung vornehmen möchten, starten Sie die Systemsteuerung, und führen Sie dann das folgende Verfahren aus:

1.  Klicken Sie auf **Clients** und dann auf **Gerätekonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** auf die Auflistung von Einstellungen, die Sie ändern möchten (beispielsweise **Global**).

3.  Legen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** den Wert des Felds **VoIP-QoS (Quality of Service)** auf **46** fest, und klicken Sie dann auf **Commit ausführen**.

Wenn Sie über mehrere Auflistungen verfügen, müssen Sie diesen Vorgang für jede Sammlung von UC-Telefoneinstellungen wiederholen. In lync Server-Systemsteuerung können Sie mehrere Einstellungsauflistungen nicht gleichzeitig ändern.

Wenn Sie Geräte haben, die nicht auf dem Windows-Betriebssystem (wie iPhones) in Ihrer Organisation basieren, werden diese Geräte nicht durch Ändern der VoiceDiffServTag-Einstellung beeinträchtigt. Wenn Sie DSCP-Werte auf diesen Geräten ändern möchten, müssen Sie sich für jeden Ihrer Gerätetypen auf das Verwaltungshandbuch berufen.

</div>

<span> </span>

</div>

</div>

</div>

