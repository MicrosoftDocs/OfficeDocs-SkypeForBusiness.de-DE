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
ms.openlocfilehash: cb4385d219173ca33ae7120dcf3e9d75d4c65f14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Erstellen und Konfigurieren von Benutzerrichtlinien für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Um die Archivierung für bestimmte Benutzer zu aktivieren oder zu deaktivieren, die sich auf lync Server befinden, müssen Sie zuerst eine Benutzerrichtlinie erstellen und dann die Richtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anwenden. Ausführliche Informationen zum Anwenden von Benutzerrichtlinien auf bestimmte Benutzer und Benutzergruppen finden Sie unter [Anwenden einer lync Server-Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.

Ausführliche Informationen zur Funktionsweise von Archivierungsrichtlinien, einschließlich der Hierarchie für Global-, Website-und Benutzerrichtlinien, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-in-situ-Speicherrichtlinien, ob die Archivierung für die Benutzer aktiviert ist, die sich in Exchange 2013 befinden, und dass ihre Postfächer in-situ-Speicher abgelegt werden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</A> in der Bereitstellungsdokumentation.<BR>Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>So konfigurieren Sie eine Archivierungsrichtlinie für Benutzer, die auf lync Server verwaltet werden

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf **Neu** und anschließend auf **Benutzerrichtlinie**.

5.  Führen Sie unter **Neue Archivierungsrichtlinie** die folgenden Aktionen aus:
    
      - Geben Sie im Feld **Name** den Namen der Benutzerrichtlinie an.
    
      - Machen Sie im Feld **Beschreibung** nähere Angaben zur Art der Benutzerrichtlinie (z. B. Benutzerrichtlinie für die Rechtsabteilung).
    
      - Um die Archivierung der internen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für die Benutzerrichtlinie zu kontrollieren, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit ausführen**.

Benutzerrichtlinien wirken sich nur auf Benutzer aus, denen eine solche Richtlinie zugewiesen wurde. Ausführliche Informationen zum Anwenden einer Benutzerrichtlinie auf bestimmte Benutzer finden Sie unter [Anwenden einer lync Server-Archivierungsrichtlinie auf einen Benutzer in lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

