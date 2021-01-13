---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 3f2ca560f934f5b907d05a1f768a0cadd8435f2a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823465"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Verhindern neuer Verbindungen mit Skype for Business Server für die Serverwartung


Skype for Business Server ermöglicht es Ihnen, einen Server offline zu schalten (z. B. um Software- oder Hardwareupgrades anzuwenden), ohne dass der Dienst für die Benutzer verloren geht.

Wenn Sie die Option zum Verhindern neuer Verbindungen oder Anrufe an einen Server innerhalb eines Pools angeben, werden keine neuen Verbindungen hergestellt oder Anrufe angenommen, sobald Sie diese Option aktivieren. Alle neuen Verbindungen und Anrufe werden an andere Server im Pool umgeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht die Fortsetzung von Sitzungen für bereits hergestellte Verbindungen, bis diese vom Benutzer beendet werden. Sobald alle vorhandenen Sitzungen beendet wurden, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, verwenden einige Skype for Business Server-Features und -Dienste den DNS-Lastenausgleich, um sicherzustellen, dass er ordnungsgemäß funktioniert. Wenn Sie für den Pool keinen DNS-Lastenausgleich verwenden, werden Verbindungen über diese Dienste während des Zeitraums, in dem der Server neue Verbindungen verhindert, möglicherweise nicht an andere Server umgeroutet, und wenn der Server offline geschaltet wird, können einige Sitzungen und Anrufe unterbrochen werden. Die folgenden Features verwenden den DNS-Lastenausgleich, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert:

  - Attendant

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ankündigungsanwendung

  - Anwendung zum Parken von Anrufen

Weitere Informationen zum DNS-Lastenausgleich finden Sie unter [Lastenausgleichsanforderungen.](../../plan-your-deployment/network-requirements/load-balancing.md)

Sie können nicht nur neue Verbindungen für alle Dienste auf einem Server mit Skype for Business Server verhindern, sondern auch neue Verbindungen für einzelne Skype for Business Server-Dienste verhindern. Diese Methode ist beispielsweise nützlich, wenn Sie ein Skype for Business Server-Update anwenden müssen, für das nicht der gesamte Server heruntergefahren werden muss. Hinweis: Wenn Sie Verbindungen für einen Dienst verhindern, müssen Sie den Dienst basierend auf der Gruppierung und Anzeige in der Windows-Liste von Diensten auswählen. Beispielsweise sind der Skype for Business Server Front-End-Dienst und der Datensammlungs-Agent für die Überwachung separate Skype for Business Server-Dienste, aber in der Liste der Windows-Dienste werden sie konsolidiert und als Skype for Business Server-Front-End-Dienst angezeigt. Sie können neue Verbindungen für den Skype for Business Server-Front-End-Dienst verhindern, aber Sie können keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden Skype for Business Server-Dienste separat verhindern.

> [!IMPORTANT]
> Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>So verhindern Sie neue Verbindungen mit Skype for Business Server

1.  Melden Sie sich als Mitglied der Gruppe Administratoren am lokalen Computer an.

2.  Öffnen Sie die Snap-In-Konsole "Dienste": Klicken Sie **auf "Start",** zeigen Sie auf "Alle **Programme",** zeigen Sie auf **"Verwaltung",** und klicken Sie dann auf **"Dienste".**

3.  Doppelklicken Sie in der Liste auf den Skype for Business Server-Windows-Dienst, mit dem Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im Eigenschaftendialogfeld unter **Dienststatus: Gestartet** auf **Anhalten**.

5.  Es empfiehlt sich, neben **Starttyp** auf **Manuell** zu klicken. Dies ist jedoch optional.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.
