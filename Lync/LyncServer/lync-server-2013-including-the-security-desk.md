---
title: 'Lync Server 2013: einschließen des Security Desks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52133ebc1e842b1f2ee3f885e038cf521fb18f3d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526622"
---
# <a name="including-the-security-desk-in-lync-server-2013"></a>Einschließen des Sicherheits Desks in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

In Ihrem Unternehmen soll möglicherweise das Sicherheitsdesk in die Konfiguration für Notrufe eingebunden werden. Um entscheiden zu können, wie das Sicherheitsdesk in Ihre E9-1-1-Bereitstellung integriert werden kann, müssen Sie die folgenden Fragen beantworten.

  - **Soll das Sicherheitsdesk benachrichtigt werden, wenn ein Notruf abgesetzt wird?**  
    Sie können die ortungsrichtlinie so konfigurieren, dass lync Server Chat Benachrichtigungen (Instant Messaging) an die lync-SIP-Adressen eines oder mehrerer Sicherheitsmitarbeiter sendet. Diese Warnungen enthalten den Namen, die Nummer und den Ort der Person, die den Notruf tätigen, und erleichtern Sicherheitspersonal bei der Unterstützung der Notfallsituation.

<!-- end list -->

  - **Möchten Sie für Notrufe eine Konferenzschaltung mit dem Sicherheitsdesk einrichten?**  
    Sofern vom Anbieter für die Notrufunterstützung unterstützt, können Sie in der Ortungsrichtlinie eine Rückrufnummer für Notrufe einschließen. Diese Nummer wird vom Anbieter verwendet, um für Notrufe eine Konferenzschaltung mit dem Sicherheitspersonal einzurichten.

<div>


> [!NOTE]  
> Falls erforderlich, können Sie für jede Ortungsrichtlinie unterschiedliches Notrufpersonal konfigurieren. Auf diese Weise können Sie die Maßnahmen für unterschiedliche Unternehmensbereiche anpassen oder ein unterschiedliches Verhalten für Notrufe konfigurieren, die von innerhalb oder von außerhalb des Netzwerks erfolgen. Geben Sie die Mitarbeiter, die benachrichtigt werden sollen, mithilfe von Verteilergruppen an.



</div>

</div>

<span> </span>

</div>

</div>

</div>

