---
title: Clientversionsrichtlinie Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden.
ms.openlocfilehash: c2d6dc4f68a7c40668db9042d420f2f341e35ca0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824895"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>Clientversionsrichtlinie: Erstellen einer neuen oder Bearbeiten einer vorhandenen Clientversionsrichtlinie

Sie können die Version von Clients angeben, die in Ihrer Umgebung unterstützt werden. Wenn zwei Clients unterschiedlicher Versionen interagieren, können die für einen der Clients verfügbaren Funktionen durch die Funktionen des anderen Clients eingeschränkt werden. Um die in Skype for Business Server enthaltenen Funktionen so gut wie sicher zu nutzen und die Benutzerfreundlichkeit insgesamt zu verbessern, können Sie den Clientversionsfilter verwenden, um die Clientversionen einzuschränken, die in Ihrer Umgebung verwendet werden. Mit dem Clientversionsfilter können Sie außerdem die Kosten senken, die aufgrund der Unterstützung mehrerer Clientversionen anfallen.

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

- **Beschreibung** Sie können eine Beschreibung hinzufügen, um die Identifizierung der Richtlinie in der Liste auf der Seite "Clientversionsrichtlinie" zu unterstützen.

- **Neu** Sie können der Richtlinie eine neue Clientversionsregel hinzufügen.

- **Details anzeigen** Mit dieser Option wird ein Dialogfeld geöffnet, in dem Sie die Optionen für eine Clientversionsregel ändern können.

- **Entfernen** Mit dieser Option wird die ausgewählte Clientversionsregel aus der Richtlinie entfernt.

- **Nach-oben-unten-Pfeile** Diese Option verschiebt die ausgewählte Clientversionsregel in der Priorität nach oben oder unten. Die Regeln werden in der angezeigten Reihenfolge verarbeitet.

Weitere Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx). Ausführliche Informationen zur Verwendung von Clientversionsrichtlinien finden Sie unter [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in der Betriebsdokumentation.

