---
title: Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der Anrufer-ID in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Anrufer-ID mithilfe der Skype for Business Server Systemsteuerung konfigurieren.'
ms.openlocfilehash: 13ca5073956e6cf67264e706a82e63ec72efbac4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865332"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die Darstellung der Anrufer-ID in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Anrufer-ID mithilfe der Skype for Business Server Systemsteuerung konfigurieren.

Mit Skype for Business Server kann die Telefonnummer des angerufenen Teilnehmers (d. h. die angerufene Telefonnummer) aus dem E.164-Format in das lokale Wählformat übersetzt werden, das vom _Trunkpeer_ (d. h. dem zugeordneten Gateway, nebenstellenanlage oder SIP-Trunk) benötigt wird. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, die die Anforderungs-URI übersetzen, bevor sie zu dem Trunk-Peer geroutet wird.

Skype for Business Server bietet Ihnen auch die Möglichkeit, die Telefonnummer des Anrufers (d. h. die Telefonnummer, aus der der Anrufer anruft) aus dem E.164-Format in das lokale Wählformat zu übersetzen, das vom Trunkpeer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe "+44" am Beginn einer Wählzeichenfolge entfernt und durch "0144" ersetzt.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>So konfigurieren Sie die Anrufer-ID mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf **Trunkkonfiguration**.

3. Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.

4. So konfigurieren Sie die Rufnummernanzeige:

   - Klicken Sie auf **Auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die für Ihre Enterprise-VoIP-Bereitstellung zur Verfügung stehen. Klicken Sie in **Übersetzungsregeln für Anrufernummern** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.

   - Wenn Sie eine neue Übersetzungsregel erstellen und dem Trunk zuordnen möchten, klicken Sie auf **Neu**. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter  ["Definieren von Übersetzungsregeln"](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in der Bereitstellungsdokumentation.

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) in der Bereitstellungsdokumentation.

   - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules).

   - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

     > [!CAUTION]
     > Weisen Sie einem Trunk keine Übersetzungsregeln zu, wenn für den zugehörigen Trunk-Peer Übersetzungsregeln konfiguriert sind. Andernfalls könnte es zu Konflikten zwischen den beiden Regeln kommen.