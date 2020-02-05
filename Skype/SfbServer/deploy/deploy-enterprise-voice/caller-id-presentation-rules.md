---
title: Erstellen oder Ändern einer Übersetzungsregel für die Anrufer-ID-Präsentation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Rufnummernanzeige mithilfe des Skype for Business Server-Control Panels konfigurieren.'
ms.openlocfilehash: d6b2e594d0f16e9b3278145087af854650a957da
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768158"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer Übersetzungsregel für die Anrufer-ID-Präsentation in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Rufnummernanzeige mithilfe des Skype for Business Server-Control Panels konfigurieren.

Mit Skype for Business Server kann die Telefonnummer des angerufenen (also die Telefonnummer) vom E. 164-Format in das lokale Wählformat übersetzt werden, das für den _trunk-Peer_ (also das zugeordnete Gateway, die Private Branch Exchange (PBX) oder den SIP-Trunk) erforderlich ist. Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

Skype for Business Server bietet Ihnen auch die Möglichkeit, die Telefonnummer des Anrufers (also die Telefonnummer, von der der Anrufer anruft) vom E. 164-Format in das lokale Wählformat zu übersetzen, das vom trunk-Peer benötigt wird. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>So konfigurieren Sie die Rufnummernanzeige mithilfe der Skype for Business Server-Systemsteuerung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.

4. So konfigurieren Sie die Rufnummernanzeige:

   - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungen auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

   - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!CAUTION]
     > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.


