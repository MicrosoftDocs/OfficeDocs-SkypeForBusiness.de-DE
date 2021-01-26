---
title: Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Zusammenfassung: Konfigurieren eines Trunks ohne aktivierte Medienumgehung für Skype for Business Server.'
ms.openlocfilehash: c7941087dc2af820969a80cf68e8d01aa4356948
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803975"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server

**Zusammenfassung:** Konfigurieren eines Trunks ohne aktivierte Medienumgehung für Skype for Business Server.

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit aktivierter Medienumgehung finden Sie unter "Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server".](configure-trunk-with-media-bypass.md)

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

### <a name="to-configure-a-trunk-without-media-bypass"></a>So konfigurieren Sie einen Trunk ohne Medienumgehung

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:

   - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.

   - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:

   - **Standort-Trunk:** Wählen Sie den Standort für diese Trunkkonfiguration in **"Standort** auswählen" aus, und klicken Sie dann auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.

   - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. Dieser Trunk kann der Stamm trunk oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.

     > [!NOTE]
     > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. > Das Feld **"Name"** wird vorab mit dem Namen des zugeordneten Standorts oder Diensts der Trunkkonfiguration aufgefüllt und kann nicht geändert werden.

4. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:

   - **Erforderlich:** Die SECURE Realtime Transport Protocol (SRTP)-Verschlüsselung muss zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch eXchange, PBX) verwendet werden.

   - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.

   - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

5. Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

6. Aktivieren  Sie das Kontrollkästchen für die zentralisierte Medienverarbeitung, wenn ein bekannter Medienendpunkt (z. B. ein PSTN-Gateway) vor ortsgleich ist, bei dem der Medienendpunkt die gleiche IP hat wie der Signalendpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

7. Wenn der Trunk-Peer den Empfang von SIP -REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen "Senden aktivieren" im **Gateway.**

8. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, der nicht von einem Skype for Business Server-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:

   - Klicken Sie auf "Auswählen", um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Bereitstellung verfügbaren ENTERPRISE-VOIP **auszuwählen.** Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

   - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.

     > [!NOTE]
     > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

     - Klicken Sie auf "Auswählen", um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.

     d. Klicken Sie auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:

     a. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

     b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:

     - Klicken Sie auf "Auswählen", um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.

     - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. Weitere Informationen finden Sie unter ["Erstellen oder Ändern einer Sprachroute in Skype for Business".](create-or-modify-a-voice-route.md)

     - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist.

     c. Klicken Sie auf **OK**.

     > [!IMPORTANT]
     > Es ist wichtig, die PstN-Verwendungseinträge entsprechend dem Vermittlungsserver-Peer zuzuordnen, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn es sich bei dem Vermittlungsserver-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zugeordnet ist, der an ein PstN-Ziel oder andere nachgelagerte Systeme, die über Skype for Business Server verbunden sind, weiterroutet.

9. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus, und klicken Sie auf die Nach-oben- oder Abwärtspfeile.

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten.

10. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

11. **Die Option "Anrufverlauf weiterleiten"** sollte aktiviert sein, um das Senden von Anrufverlaufsinformationen an den Gateway-Peer des Vermittlungsservers zu aktivieren.

12. **Die Weiterleitung von P-Asserted-Identity-Daten** sollte aktiviert werden, um die Weiterleitung von Informationen zum Ermittler von PAI zwischen dem Vermittlungsserver und gatewayseitig (und umgekehrt) zu ermöglichen, wenn vorhanden.

13. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Das erneute Umleitung an einen anderen Trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.

14. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die wählende Nummer angewendet.

    - Klicken Sie auf "Auswählen", um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP **verfügbar sind.** Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zu Übersetzungsregeln finden Sie unter [Übersetzungsregeln in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

      > [!CAUTION]
      > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.

    - Klicken Sie auf "Auswählen", um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP **verfügbar sind.** Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zu Übersetzungsregeln finden Sie unter [Übersetzungsregeln in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

      > [!CAUTION]
      > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

16. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie dann auf den Pfeil nach oben oder unten.

    > [!IMPORTANT]
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel mit einer beliebigen elfstelligen Nummer und eine Übersetzungsregel eingeschlossen haben, die nur mit 11-stelligen Nummern, die mit  +1425 beginnen, entspricht, stellen Sie sicher, dass die Regel, die einer beliebigen elfstelligen Nummer entspricht, unterhalb der restriktiveren Regel sortiert ist.

17. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

18. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Weitere Informationen

[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md)

[Definieren von Übersetzungsregeln](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

