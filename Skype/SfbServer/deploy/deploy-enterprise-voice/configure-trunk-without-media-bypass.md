---
title: 'Skype for Business Server: Konfigurieren eines Trunks ohne Medienumgehung'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Zusammenfassung: Konfigurieren eines Trunks ohne medienumgehung für Skype for Business Server aktiviert.'
ms.openlocfilehash: 2f6edcf34f7da82da53ca10b523468b4ba794209
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590579"
---
# <a name="skype-for-business-server-configure-a-trunk-without-media-bypass"></a>Skype for Business Server: Konfigurieren eines Trunks ohne Medienumgehung

**Zusammenfassung:** Konfigurieren Sie einen Trunk ohne medienumgehung für Skype for Business Server aktiviert.

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen Trunk mit aktivierter Medienumgehung konfigurieren möchten, lesen Sie die Informationen unter [Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server.](configure-trunk-with-media-bypass.md)

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

### <a name="to-configure-a-trunk-without-media-bypass"></a>So konfigurieren Sie einen Trunk ohne Medienumgehung

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:

   - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.

   - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:

   - **Standorttrunk:** Wählen Sie den Standort für diese Trunkkonfiguration in **"Standort auswählen"** aus, und klicken Sie dann auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.

   - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. Dieser Trunk kann der Stammtrunk oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.

     > [!NOTE]
     > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. > Das **Feld "Name"** ist mit dem Namen des zugeordneten Standorts oder Diensts der Trunkkonfiguration vorgefüllt und kann nicht geändert werden.

4. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:

   - **Erforderlich:** Die SRTP-Verschlüsselung (Secure Realtime Transport Protocol) muss verwendet werden, um den Datenverkehr zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch eXchange) zu schützen.

   - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.

   - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

5. Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

6. Aktivieren Sie das Kontrollkästchen **"Zentrale Medienverarbeitung",** wenn ein bekannter Medienendpunkt vorhanden ist (z. B. ein PSTN-Gateway (Public Switched Telephone Network), bei dem die Medienendung dieselbe IP wie der Signalendpunkt aufweist. Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

7. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das **Kontrollkästchen Senden aktivieren über das Kontrollkästchen Gateway.**

8. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, der nicht von einem Skype for Business Server-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:

   - Klicken Sie auf **"Auswählen",** um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

   - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

     - Klicken Sie auf **"Auswählen",** um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

     - Klicken Sie auf **"Auswählen",** um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern einer VoIP-Route in Skype for Business.](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.

     c. Klicken Sie auf **OK**.

     > [!IMPORTANT]
     > Es ist wichtig, PSTN-Verwendungsdatensätze gemäß dem Vermittlungsserverpeer zuzuordnen, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn der Vermittlungsserverpeer ein PSTN-Gateway oder ein Session Border Controller (SBC) ist, wird dringend empfohlen, die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zuzuordnen, der an ein PSTN-Ziel oder andere downstreame Systeme, die über Skype for Business Server verbunden sind, leitet.

9. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, wählen Sie den PSTN-Verwendungsdatensatz aus, und klicken Sie auf die Pfeile nach oben oder unten.

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten.

10. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

11. **Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.

12. **Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.

13. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Eine Umleitung zu einem anderen Trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.

14. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die wählende Nummer angewendet.

    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie unter ["Übersetzungsregeln" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

      > [!CAUTION]
      > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.

    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie unter ["Übersetzungsregeln" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

      > [!CAUTION]
      > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

16. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Um die Position einer Regel in der Liste zu ändern, markieren Sie den Regelnamen, und klicken Sie dann auf den Pfeil nach oben oder unten.

    > [!IMPORTANT]
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel eingefügt haben, die einer beliebigen 11-stelligen Nummer entspricht, und eine Übersetzungsregel, die nur mit 11-stelligen Nummern übereinstimmt, die mit +1425 beginnen, stellen Sie sicher, dass die Regel, die einer 11-stelligen Nummer entspricht,  *unterhalb*  der restriktiveren Regel sortiert ist.

17. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

18. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Definieren von Übersetzungsregeln](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)