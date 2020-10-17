---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für die Archivierung'
description: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für die Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8f8125f458c4269626e0b1c929f2acb1a8de0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556861"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Wenn Sie Ihre Front-End-Server bereitstellen, erstellt lync Server eine globale Richtlinie für die Archivierung. Standardmäßig ist die Archivierung in der globalen Richtlinie deaktiviert. Die globale Richtlinie steuert, ob die Archivierung für die interne und externe Kommunikation für Ihre gesamte Bereitstellung aktiviert ist, es sei denn, Sie richten Standort-oder Benutzerrichtlinien ein, die die globale Richtlinie außer Kraft setzen oder wenn Sie Microsoft Exchange Integration für einige oder alle Benutzer verwenden. Wenn Sie Microsoft Exchange Integration verwenden, gilt die globale Richtlinie nicht für Benutzer, die in Exchange 2013 verwaltet werden und die Postfächer In-Place halten.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>So konfigurieren Sie die globale Richtlinie für die Archivierung zur Verwendung der Lync Server-Archivierungsdatenbanken

1.  Melden Sie sich mit einem Benutzerkonto, dem die CsArchivingAdministrator- oder die CsAdministrator-Rolle zugewiesen wurde, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Edit** und dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
      - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.
    
      - Geben Sie im Feld **Beschreibung** Informationen zur Gestalt der Richtlinie ein (z. B. globale Richtlinie für *Abteilungsname*).
    
      - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

