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
ms.openlocfilehash: aa8068b69afa3e02a5634041c61be6f7711e8f30
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>Konfigurieren der Dienstqualität auf Microsoft lync Phone Edition-Geräten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Obwohl QoS (Quality of Service) nicht standardmäßig für Geräte wie iPhones aktiviert ist, ist QoS standardmäßig für Geräte mit lync Phone Edition aktiviert. (Diese Geräte werden gemeinhin als UC-oder Unified Communication-Telefone bezeichnet.) Führen Sie den folgenden Windows PowerShell-Befehl in der lync Server-Verwaltungsshell aus, um dies zu überprüfen:

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

Für Quality of Service-Zwecke ist nur eine dieser Eigenschaften von Interesse: VoiceDiffServTag. VoiceDiffServTag stellt den DSCP-Wert dar, der dem VoIP-Datenverkehr zugewiesen ist, der von einem lync Phone Edition-Gerät ausgeht.

<div>


> [!NOTE]
> Der Voice8021p-Parameter wird in lync Server 2013 nicht mehr unterstützt. Der Parameter ist nach wie vor aus Gründen der Abwärtskompatibilität mit Microsoft lync Server 2010 gültig. Sie hat jedoch keine Auswirkungen auf Geräte, die mit lync Server 2013 verwendet werden.



</div>

In den meisten Netzwerken sollten die Kennzeichnung von lync Phone Edition-Paketen mit einem VoiceDiffServTag von 40 keine Probleme verursachen. 40 ist jedoch nicht der in der Regel für den Audioverkehr verwendete Wert; Stattdessen wird der Audioverkehr fast immer mit dem DSCP-Code 46 markiert. Um die Konsistenz im gesamten Netzwerk zu gewährleisten, sollten Sie die VoiceDiffServTag-Eigenschaft Ihrer UC-Telefone in 46 ändern.

Dazu können Sie entweder Windows PowerShell oder die lync Server-Systemsteuerung verwenden. Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um den VoiceDiffServTag-Wert mithilfe von Windows PowerShell zu ändern:

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Mit dem vorhergehenden Befehl wird die globale Sammlung der UC-Telefon Konfigurationseinstellungen geändert. Beachten Sie jedoch, dass die Einstellungen für UC-Telefone auch dem Website Bereich zugewiesen werden können. Wenn Sie die Einstellungen für die UC-Telefon Konfiguration im Website Bereich ändern möchten, müssen Sie die Websiteidentität angeben. Beispiel:

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

Sie können auch den folgenden Befehl verwenden, um alle Ihre UC-Telefon Konfigurationseinstellungen gleichzeitig zu ändern:

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

Wenn Sie diese Änderung lieber mithilfe der lync Server-Systemsteuerung vornehmen möchten, starten Sie die Systemsteuerung, und führen Sie dann das folgende Verfahren aus:

1.  Klicken Sie auf **Clients** , und klicken Sie dann auf **Gerätekonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Gerätekonfiguration** auf die Sammlung von Einstellungen, die Sie ändern möchten (beispielsweise **Global**).

3.  Legen Sie im Dialogfeld **Gerätekonfiguration bearbeiten** den Wert für **Quality of Service (QoS) für Voicemail** auf **46** fest, und klicken Sie dann auf **Commit**.

Wenn Sie über mehrere Sammlungen verfügen, müssen Sie diesen Vorgang für jede Sammlung von UC-Telefoneinstellungen wiederholen. In der lync Server-Systemsteuerung können Sie mehrere Einstellungsauflistungen nicht gleichzeitig ändern.

Wenn Sie Geräte haben, die nicht auf dem Windows-Betriebssystem (wie iPhones) in Ihrer Organisation basieren, sind diese Geräte durch Ändern der VoiceDiffServTag-Einstellung nicht betroffen. Wenn Sie DSCP-Werte auf diesen Geräten ändern möchten, müssen Sie für jeden Ihrer Gerätetypen auf das Verwaltungshandbuch verweisen.

</div>

<span> </span>

</div>

</div>

</div>

