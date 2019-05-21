---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b7aa303f2b49a806434af91789ab3e610fdc45c0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279487"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Verhindern neuer Verbindungen mit Skype for Business Server für die Serverwartung


Mit Skype for Business Server können Sie einen Server offline schalten (beispielsweise um Software-oder Hardware-Upgrades anzuwenden), ohne dass der Service für die Nutzer verloren geht.

Wenn Sie die Option zum verhindern neuer Verbindungen oder Aufrufe an einen Server in einem Pool angeben, werden alle neuen Verbindungen und Anrufe nicht mehr Unternehmen, sobald Sie diese Option implementieren. Diese neuen Verbindungen und Anrufe werden über andere Server im Pool weitergeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht, dass seine Sitzungen an vorhandenen Verbindungen fortgesetzt werden, bis Sie natürlich enden. Wenn alle vorhandenen Sitzungen beendet sind, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, Vertrauen einige Funktionen und Dienste von Skype for Business Server auf den DNS-Lastenausgleich, um sicherzustellen, dass Sie ordnungsgemäß funktioniert. Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, werden Verbindungen über diese Dienste möglicherweise während des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet, und wenn der Server offline geschaltet wird, werden einige Sitzungen und Anrufe möglicherweise unterbrochen. Die Features, die vom DNS-Lastenausgleich abhängig sind, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, sind wie folgt:

  - Vermittlung

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ansageanwendung

  - Anwendung zum Parken von Anrufen

Details zum DNS-Lastenausgleich finden Sie unter [Lastenausgleichsanforderungen](../../plan-your-deployment/network-requirements/load-balancing.md).

Zusätzlich zur Verhinderung neuer Verbindungen für alle Dienste auf einem Server, auf dem Skype for Business Server ausgeführt wird, können Sie auch neue Verbindungen für einzelne Skype for Business Server-Dienste verhindern. Diese Methode ist beispielsweise hilfreich in einer Situation, in der Sie ein Skype for Business Server-Update anwenden müssen, das nicht erfordert, dass der gesamte Server beendet wird. Beachten Sie, dass Sie einen Dienst auswählen müssen, wenn Sie Verbindungen für einen Dienst verhindern, indem Sie ihn gruppieren und in der Windows-Liste der Dienste angezeigt werden. Beispielsweise sind der Skype for Business Server-Front-End-Dienst und der Datenerfassungs-Agent für die Überwachung getrennte Skype for Business Server-Dienste, in der Windows-Diensteliste werden Sie jedoch konsolidiert und als Skype for Business Server-Front-End angezeigt. Dienst. Sie können neue Verbindungen für den Skype for Business Server-Front-End-Dienst verhindern, aber Sie können keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden Skype for Business Server-Dienste separat verhindern.

> [!IMPORTANT]
> Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren. Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>So verhindern Sie neue Verbindungen mit Skype for Business Server

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Öffnen Sie die Snap-In-Konsole Dienste: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Doppelklicken Sie in der Liste auf den Skype for Business Server-Windows-Dienst, auf den Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im DialogfeldEigenschaften unter **Dienststatus: gestartet**auf **Anhalten**.

5.  Optional, aber empfohlen, klicken Sie **** neben Starttyp auf **manuell**.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren. Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.
