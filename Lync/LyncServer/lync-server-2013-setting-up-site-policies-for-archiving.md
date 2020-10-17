---
title: 'Lync Server 2013: Einrichten von Standortrichtlinien für die Archivierung'
description: 'Lync Server 2013: Einrichten von Standortrichtlinien für die Archivierung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e5b80b7f62ddc18d418415307457c7f2c4010d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558391"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a>Einrichten von Standortrichtlinien für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Sie können die Archivierung für bestimmte Websites aktivieren oder deaktivieren, indem Sie für jede dieser Websites eine Archivierungsrichtlinie erstellen und konfigurieren. Eine Standortrichtlinie setzt die globale Richtlinie außer Kraft, aber Benutzerrichtlinien überschreiben Standortrichtlinien. Archivierungsrichtlinien gelten nur, wenn Sie nicht Microsoft Exchange Integration verwenden oder, wenn Sie Microsoft Exchange-Integration verwenden, aber einige Benutzer haben, die nicht in Exchange 2013 verwaltet werden und deren Postfächer In-Place Aufbewahrungsstelle gespeichert werden.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktivieren, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.<BR>Geben Sie in den Archivierungskonfigurationen erst alle erforderlichen Optionen, bevor Sie in den Archivierungsrichtlinien die Archivierung der internen oder externen Kommunikation aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a>So erstellen Sie eine Archivierungsrichtlinie für einen Standort

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.
    
    Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.

4.  Klicken Sie auf **Neu** und anschließend auf **Standortrichtlinie**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll.

6.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
      - Geben Sie im Feld **Name** den Namen für die Standortrichtlinie an.
    
      - Geben Sie im Feld **Beschreibung** Informationen zum Verwendungszweck der Standortrichtlinie an (z. B. Standortrichtlinie für Redmond).
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**, um die Archivierung der internen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.
    
      - Aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**, um die Archivierung der externen Kommunikation für den angegebenen Standort zu aktivieren oder zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

