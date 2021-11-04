---
title: 'Skype for Business Server: Konfigurieren eines Trunks mit Medienumgehung'
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 'Zusammenfassung: Konfigurieren eines Trunks mit aktivierter Medienumgehung für Skype for Business Server. Auf diese Weise können Sie die Anzahl der Vermittlungsserver minimieren, wobei davon aus wird, dass ihr SIP-Trunkanbieter dies unterstützt.'
ms.openlocfilehash: aeb65216a3d001d4fe78808985a1010c23427277
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753826"
---
# <a name="skype-for-business-server-configure-a-trunk-with-media-bypass"></a>Skype for Business Server: Konfigurieren eines Trunks mit Medienumgehung

**Zusammenfassung:** Konfigurieren Sie einen Trunk mit aktivierter Medienumgehung für Skype for Business Server. Auf diese Weise können Sie die Anzahl der Vermittlungsserver minimieren, wobei davon aus wird, dass ihr SIP-Trunkanbieter dies unterstützt.

Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit deaktivierter Medienumgehung finden Sie unter [Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server.](configure-trunk-without-media-bypass.md)

Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Weitere Informationen finden Sie unter [Planen der Medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Es wird dringend empfohlen, die Medienumgehung zu aktivieren. Bevor Sie jedoch die Medienumgehung für einen SIP-Trunk aktivieren, vergewissern Sie sich, dass Ihr qualifizierter SIP-Trunkanbieter die Medienumgehung unterstützt und die Anforderungen für die erfolgreiche Aktivierung des Szenarios erfüllen kann. Insbesondere muss der Anbieter über die IP-Adressen der Server im internen Netzwerk Ihrer Organisation verfügen.

> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem PSTN-Gateway, jeder IP-Nebenstellenanlage und jedem Session Border Controller (SBC). Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet. Die Medienumgehung wird nur für Produkte und Versionen unterstützt, die auf der Seite ["Telefonieinfrastruktur für Skype for Business Server"](../../../SfbPartnerCertification/certification/infra-gateways.md) aufgeführt sind.

Eine Trunkkonfiguration, wie unten beschrieben, gruppiert eine Reihe von Parametern, die auf Trunks angewendet werden, denen diese Trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

### <a name="to-configure-a-trunk-with-media-bypass"></a>So konfigurieren Sie einen Trunk mit Medienumgehung

1. Öffnen Skype for Business Server Systemsteuerung

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:

   - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.

   - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:

   - **Standorttrunk:** Wählen Sie den Standort für diese Trunkkonfiguration aus **"Standort auswählen"** aus, und klicken Sie dann auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.

   - **Pooltrunk:** Wählen Sie den Namen des Trunks aus, für den diese Trunkkonfiguration gilt. Dieser Trunk kann der Stammtrunk oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Klicken Sie unter **"Dienst auswählen"** auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.

      > [!NOTE]
      > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. > Das **Feld "Name"** wird mit dem Namen des zugeordneten Standorts oder Diensts der Trunkkonfiguration vorgefüllt und kann nicht geändert werden.

4. Geben Sie einen Wert in **maximal unterstützten frühen Dialogfeldern** an. Dies ist die maximale Anzahl verzweigter Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) von ITSP an eine INVITE empfangen kann, die an den Vermittlungsserver gesendet wird. Der Standardwert lautet 20.

    > [!NOTE]
    > Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten.

5. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:

   - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.

   - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.

   - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

6. Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.

    > [!IMPORTANT]
    > Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen. Ausführliche Informationen finden Sie unter [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

8. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das **Kontrollkästchen Senden aktivieren über das Kontrollkästchen Gateway.**

    > [!NOTE]
    > Wenn Sie diese Option deaktivieren, während die Option **Medienumgehung aktivieren** ausgewählt ist, sind zusätzliche Einstellungen erforderlich. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet **Set-CsTrunkConfiguration** ausführen, um RTCP für aktive und gehaltene Anrufe zu deaktivieren, um geeignete Bedingungen für die Medienumgehung zu schaffen. Alternativ können Sie **"Refer aktivieren" mithilfe der Drittanbieteranrufsteuerung** auswählen, wenn übertragene Anrufe medienumgehungen werden sollen und das Gateway keine SIP REFER-Anforderungen unterstützt.

9. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, der nicht von einem Skype for Business Server Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:

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

10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um die Position eines Datensatzes in der Liste zu ändern, wählen Sie den PSTN-Verwendungsdatensatz aus, und klicken Sie auf die Pfeile nach oben oder unten.

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten.

11. **Aktivieren Sie die RTP-Verriegelung,** um Medienumgehung für Clients hinter einer Netzwerkadressübersetzung (NETWORK Address Translation, NAT) oder Firewall und einem SBC zu aktivieren, der die Verriegelung unterstützt.

12. **Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.

13. **Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.

14. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird, erfolgt eine Umleitung zu einem anderen Trunk. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.

15. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die wählende Nummer angewendet.

    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie [unter "Übersetzungsregeln" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!CAUTION]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.

    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie unter ["Übersetzungsregeln" in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)

    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist.

    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**.

    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!CAUTION]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können.

17. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Um die Position einer Regel in der Liste zu ändern, markieren Sie den Regelnamen, und klicken Sie dann auf den Pfeil nach oben oder unten.

    > [!IMPORTANT]
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel eingefügt haben, die einer beliebigen 11-stelligen Nummer entspricht, und eine Übersetzungsregel, die nur mit 11-stelligen Nummern übereinstimmt, die mit +1425 beginnen, stellen Sie sicher, dass die Regel, die einer 11-stelligen Nummer entspricht,  *unterhalb*  der restriktiveren Regel sortiert ist.

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Skype for Business](voice-route-config-changes.md) in der Betriebsdokumentation.

Nachdem Sie den Trunk konfiguriert haben, setzen Sie die Konfiguration der Medienumgehung fort, indem Sie zwischen den Optionen für die globale Medienumgehung auswählen, wie unter [Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md) in der Bereitstellungsdokumentation beschrieben.
## <a name="see-also"></a>Weitere Informationen

[Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server](configure-trunk-without-media-bypass.md)

[Bereitstellen der Medienumgehung in Skype for Business Server](deploy-media-bypass.md)

[Definieren von Übersetzungsregeln](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

[Konfigurieren der Medienumgehung](/previous-versions/office/lync-server-2013/lync-server-2013-configure-media-bypass)