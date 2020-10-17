---
title: Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40425957d472da2d31d91472634f268dde5b8c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504672"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Zum Aktivieren oder Deaktivieren der Archivierung für bestimmte Benutzer, die in lync Server verwaltet werden, müssen Sie zuerst eine Benutzerrichtlinie erstellen und dann die Richtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Ausführliche Informationen zum Anwenden von Benutzerrichtlinien auf bestimmte Benutzer und Benutzergruppen finden Sie unter [Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für globale, Standort-und Benutzerrichtlinien, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-In-Place-Aufbewahrungsrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und dass ihre Postfächer In-Place Aufbewahrungsspeicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.<BR>Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>So konfigurieren Sie eine Archivierungsrichtlinie für Benutzer, die in lync Server verwaltet werden

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.

5.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Schritte aus:
    
      - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.
    
      - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
      - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit**.

Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde. Ausführliche Informationen zum Anwenden einer Benutzerrichtlinie auf bestimmte Benutzer finden Sie unter [Anwenden einer lync Server Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

