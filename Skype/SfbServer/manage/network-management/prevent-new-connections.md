---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: c776c915247533641bc92d1a5458daf671bf6a04
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759727"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Verhindern neuer Verbindungen mit Skype for Business Server für die Serverwartung


Skype for Business Server ermöglicht es Ihnen, einen Server offline zu schalten (z. B. Software- oder Hardwareupgrades) ohne Dienstausfall für Benutzer.

Wenn Sie die Option zum Verhindern neuer Verbindungen oder Anrufe an einen Server innerhalb eines Pools angeben, werden keine neuen Verbindungen hergestellt oder Anrufe angenommen, sobald Sie diese Option aktivieren. Alle neuen Verbindungen und Anrufe werden an andere Server im Pool umgeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht die Fortsetzung von Sitzungen für bereits hergestellte Verbindungen, bis diese vom Benutzer beendet werden. Sobald alle vorhandenen Sitzungen beendet wurden, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, verwenden einige Skype for Business Server Features und Dienste den DNS-Lastenausgleich, um sicherzustellen, dass er ordnungsgemäß funktioniert. Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, werden Verbindungen über diese Dienste möglicherweise während des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet, und wenn der Server offline geschaltet wird, können einige Sitzungen und Anrufe unterbrochen werden. Die Funktionen, die auf DNS-Lastenausgleich basieren, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, sind wie folgt:

  - Attendant

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ankündigungsanwendung

  - Anwendung zum Parken von Anrufen

Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter ["Lastenausgleichsanforderungen".](../../plan-your-deployment/network-requirements/load-balancing.md)

Zusätzlich zur Verhinderung neuer Verbindungen für alle Dienste auf einem Server, auf dem Skype for Business Server ausgeführt wird, können Sie auch neue Verbindungen für einzelne Skype for Business Server Dienste verhindern. Diese Methode ist beispielsweise in Situationen nützlich, in denen Sie ein Skype for Business Server Update anwenden müssen, bei dem nicht der gesamte Server heruntergefahren werden muss. Hinweis: Wenn Sie Verbindungen für einen Dienst verhindern, müssen Sie den Dienst basierend auf der Gruppierung und Anzeige in der Windows-Liste von Diensten auswählen. Beispielsweise sind der Skype for Business Server Front-End Dienst und der Datensammlungs-Agent für die Überwachung separate Skype for Business Server Dienste, aber in der Liste der Windows Dienste werden sie konsolidiert und als Skype for Business Server Front-End angezeigt. Service. Sie können neue Verbindungen für den Skype for Business Server Front-End-Dienst verhindern, jedoch keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden Skype for Business Server Dienste separat.

> [!IMPORTANT]
> Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>So verhindern Sie neue Verbindungen mit Skype for Business Server

1.  Melden Sie sich beim lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Öffnen Sie die Snap-In-Konsole "Dienste": Klicken Sie auf **"Start",** zeigen Sie auf **"Alle Programme",** zeigen Sie auf **"Verwaltungstools",** und klicken Sie dann auf **"Dienste".**

3.  Doppelklicken Sie in der Liste auf den Skype for Business Server Windows Dienst, mit dem Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im Eigenschaftendialogfeld unter **Dienststatus: Gestartet** auf **Anhalten**.

5.  Es empfiehlt sich, neben **Starttyp** auf **Manuell** zu klicken. Dies ist jedoch optional.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.
