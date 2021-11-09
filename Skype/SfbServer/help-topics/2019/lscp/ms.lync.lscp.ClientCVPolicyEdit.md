---
title: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.
ms.openlocfilehash: a3549bc94cc886526610c40ee4cddb75310ebe74
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840527"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Clientversionsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie

Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Um die in Skype for Business Server enthaltenen Features am besten zu nutzen und die Gesamtbenutzererfahrung zu verbessern, können Sie den Clientversionsfilter verwenden, um die in Ihrer Umgebung verwendeten Clientversionen einzuschränken. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.

> [!IMPORTANT]
> Filter werden gemäß ihrer Rangfolge aufgelistet. Beispiel: Sie verfügen über einen Filter, der die Ausführung von Clientversion 1.5 zulässt, gefolgt von einem Filter, der Clients mit früheren Versionen als Version 2.0 blockiert. In diesem Fall hat der erste Filter Vorrang, und Clients mit Version 1.5 können eine Verbindung herstellen.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionsrichtlinie** oder **Clientversionsrichtlinie bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen oder Ändern des Namens oder der Beschreibung der Clientversionsrichtlinie

- Hinzufügen oder Ändern der Clientversionsregeln für die Clientversionsrichtlinie

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Bereich** Gibt den Bereich (Standort, Pool oder Benutzer) der Clientversionsrichtlinie an.

- **Name** Sie können den Namen der Clientversionsrichtlinie hinzufügen oder ändern.

- **Beschreibung** Sie können eine Beschreibung hinzufügen, um die Richtlinie in der Liste auf der Seite "Clientversionsrichtlinie" zu identifizieren.

- **Neu** Sie können der Richtlinie eine neue Clientversionsregel hinzufügen.

- **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine Clientversionsregel ändern können.

- **Entfernen** Mit dieser Option wird die ausgewählte Clientversionsregel aus der Richtlinie entfernt.

- **Pfeile nach oben und unten** Mit dieser Option wird die ausgewählte Clientversionsregel in der Priorität nach oben oder unten verschoben. Die Regeln werden in der angezeigten Reihenfolge verarbeitet.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter ["Client-Interoperabilität".](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) Ausführliche Informationen zur Verwendung von Clientversionsrichtlinien finden Sie unter [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in der Betriebsdokumentation.