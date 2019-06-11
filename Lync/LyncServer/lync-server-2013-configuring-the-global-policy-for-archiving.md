---
title: 'Lync Server 2013: Konfigurieren der globalen Richtlinie für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccb5ba267c3dc94e14f00cf96f240fa2f0e91b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a>Konfigurieren der globalen Richtlinie für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Sie Ihre Front-End-Server bereitstellen, erstellt lync Server eine globale Richtlinie für die Archivierung. Standardmäßig ist die Archivierung in der globalen Richtlinie deaktiviert. Mit der globalen Richtlinie wird gesteuert, ob die Archivierung für die interne und externe Kommunikation für Ihre gesamte Bereitstellung aktiviert ist, es sei denn, Sie richten Website-oder Benutzerrichtlinien ein, die die globale Richtlinie außer Kraft setzen, oder wenn Sie die Microsoft Exchange-Integration für einige oder alle von Ihre Benutzer. Wenn Sie die Microsoft Exchange-Integration verwenden, gilt die globale Richtlinie nicht für Benutzer, die sich in Exchange 2013 befinden und die Postfächer in-situ-Speicher aufbewahren.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in der lync Server 2013](lync-server-2013-how-archiving-works.md) -Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a>So konfigurieren Sie die globale Richtlinie für die Archivierung bei Verwendung der lync Server-Archivierungsdatenbanken

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Bearbeiten** und dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
      - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen „Global“ nicht verwenden möchten.
    
      - Geben Sie im Feld **Beschreibung** Informationen zur Gestalt der Richtlinie ein (z. B. globale Richtlinie für *Abteilungsname*).
    
      - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert werden, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

