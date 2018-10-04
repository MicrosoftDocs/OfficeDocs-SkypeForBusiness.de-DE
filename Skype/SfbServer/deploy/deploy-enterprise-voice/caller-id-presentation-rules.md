---
title: Erstellen oder Ändern einer übersetzungsregel für Rufnummernanzeige in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren der Anrufer-ID mithilfe der Skype für Business Server-Systemsteuerung.'
ms.openlocfilehash: 69d5a1d8f04900933b5de4ebd795961d8b450ca7
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373587"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>Erstellen oder Ändern einer übersetzungsregel für Rufnummernanzeige in Skype für Business Server

**Zusammenfassung:** Informationen Sie zum Konfigurieren der Anrufer-ID mithilfe der Skype für Business Server-Systemsteuerung.

Mit Skype für Business Server Telefonnummer des angerufenen (d. h., die Telefonnummer genannt) aus dem e. 164-Format übersetzt werden kann, um die lokale Wählformat, die durch den _trunkpeer_ (d. h., die zugehörigen Gateway, private Branch Exchange (erforderlich ist PBX) oder SIP-Trunk). Dazu müssen Sie eine oder mehrere Übersetzungsregeln definieren, um den Anforderungs-URI vor dem Routen an den Trunkpeer zu übersetzen.

Skype für Business Server haben Sie auch die Möglichkeit, auch die Rufnummer des Anrufers (d. h., die Telefonnummer, die der Aufrufer den Aufruf ausführt) übersetzen aus dem e. 164-Format an das lokale Wählformat, das durch den trunkpeer erforderlich ist. So können Sie zum Beispiel eine Übersetzungsregel schreiben, die die Angabe „+44“ am Beginn einer Wählzeichenfolge entfernt und durch „0144“ ersetzt.

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>So konfigurieren Sie die Anrufer-ID mithilfe von Skype Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Doppelklicken Sie auf der Seite **Trunkkonfiguration** auf einen vorhandenen Trunk (z. B. auf den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** zu öffnen.

4. So konfigurieren Sie die Rufnummernanzeige:

   - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln in Ihrer Bereitstellung von Enterprise-VoIP verfügbar auszuwählen, klicken Sie auf **auswählen**. Klicken Sie in **Übersetzungsregeln für die wählende Nummer** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Weitere Informationen hierzu finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in der Bereitstellungsdokumentation.

   - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen hierzu finden Sie unter [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).

   - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!CAUTION]
     > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.


