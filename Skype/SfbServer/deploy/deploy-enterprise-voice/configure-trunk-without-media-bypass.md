---
title: Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Zusammenfassung: Konfigurieren eines Trunks ohne medienumgehung für Skype für Business Server aktiviert.'
ms.openlocfilehash: fa912286dd89acaa75781d8175f6820444adc6ea
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884175"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server

**Zusammenfassung:** Konfigurieren eines Trunks ohne medienumgehung für Skype für Business Server aktiviert.

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen Trunk mit medienumgehung konfigurieren möchten, finden Sie unter [Konfigurieren eines Trunks mit Medien in Skype für Business Server umgehen](configure-trunk-with-media-bypass.md).

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globaler Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

### <a name="to-configure-a-trunk-without-media-bypass"></a>So konfigurieren Sie einen Trunk ohne Medienumgehung

1. Öffnen von Skype Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.

3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:

   - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.

   - Klicken Sie auf **Neu** und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:

   - **Website-Trunk**: Wählen Sie die Website für dieser trunkkonfiguration im **Dialogfeld Standort auswählen**, und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.

   - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. In diesem Trunk kann der stammtrunk oder alle zusätzlichen Trunks im Topologie-Generator definiert sein. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird der Trunk nicht im Dialogfeld **Dienst auswählen** angezeigt.

    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. > Im Feld **Name** wird durch den Namen des der trunkkonfiguration zugeordneten Standorts oder Diensts vorab aufgefüllt und kann nicht geändert werden.

4. Wählen Sie unter **Verschlüsselungsunterstützungsgrad** eine der folgenden Optionen aus:

   - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.

   - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.

   - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.

5.  Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.

6. Aktivieren Sie das Kontrollkästchen **Zentralisierte Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.

7. Wenn Sie der trunkpeer das Empfangen von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden der Weiterleitung an das Gateway aktivieren** .

8. (Optional) Für die Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu und konfigurieren Sie diese. Dieser trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, die nicht von einem Skype für Business Server Endpunkt stammt. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eins der folgenden Verfahren nutzen:

   - Um einen oder mehrere Datensätze aus einer Liste aller PSTN-verwendungsdatensätzen in Ihrer Bereitstellung von Enterprise-VoIP verfügbar auszuwählen, klicken Sie auf **auswählen**. Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Markieren Sie einen Datensatz und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.

   - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:

     a. Klicken Sie auf **Neu**.

     b. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.

     > [!NOTE]
     > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden.

     c. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

     - Um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Bereitstellung von Enterprise-VoIP ausgewählt haben, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.

     - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

     - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**.

     d. Klicken Sie anschließend auf **OK**.

   - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:

    a. Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.

    b. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Datensatz zuzuordnen und zu konfigurieren:

     - Um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Bereitstellung von Enterprise-VoIP ausgewählt haben, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**.

     - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.

     - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. Weitere Informationen hierzu finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).

     - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**.

    c. Klicken Sie anschließend auf **OK**.

     > [!IMPORTANT]
     > Es ist wichtig, um PSTN-verwendungsdatensätzen entsprechend der Vermittlungsserver Peer zuzuordnen, die den konfigurierten Trunk zugeordnet ist. Wenn der Vermittlungsserver Peer ein PSTN-Gateway oder ein Session Border Controller (SBC) ist, wird dringend empfohlen, dass die trunkkonfiguration nicht mit einem PSTN-Datensatz verknüpft ist, die über Skype-Routen für ein PSTN-Ziel oder eine beliebige andere downstream-Systemen verbunden für Business Server.

9. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Um einen Datensatz Position in der Liste zu ändern, wählen Sie den PSTN-Datensatz, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Tasten aus.

    > [!IMPORTANT]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Skype für Business Server durchläuft die Liste von oben nach unten.

10. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.

11. **Weiterleitung des Anrufverlaufs aktivieren** sollte ausgewählt sein, damit das Senden von anrufverlaufsinformationen an dem gatewaypeer des Vermittlungsservers.

12. **Weiterleiten von P-Asserted-Identity-Daten aktivieren** sollte ausgewählt sein, damit PAI Informationen zwischen der vermittlungsserverseite und der gatewayseite weitergeleitet werden (und umgekehrt), bei der Vorstellung.

13. **Failovertimer für Ausgangsrouting aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Weiterleitung an einen anderen Trunk auftreten, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.

14. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln gelten für anrufende Nummern für ausgehende Anrufe

   - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln auszuwählen, die in der Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

   - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie unter [Übersetzungsregeln in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.

   - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!CAUTION]
     > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.

15. (Optional) Ordnen Sie **Übersetzungsregeln für die gewählte Nummer** für den Trunk zu und konfigurieren Sie diese. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf.

   - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln auszuwählen, die in der Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.

  - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zu Übersetzungsregeln finden Sie unter [Übersetzungsregeln in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist.

   - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**.

   - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

     > [!CAUTION]
     > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten.

16. Stellen Sie sicher, dass der Trunk Übersetzungsregeln in der richtigen Reihenfolge angeordnet sind. Um eine Regel Position in der Liste zu ändern, markieren Sie den Regelnamen, und klicken Sie auf den Pfeil nach oben oder nach-unten Sie-Pfeil.

    > [!IMPORTANT]
    > Skype für Business Server durchläuft die Liste der Übersetzung von oben nach unten und verwendet die erste Regel, die mit die gewählte Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehreren Übersetzungsregeln übereinstimmen kann, müssen Sie sicherstellen, dass die stärker einschränkenden Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie eine übersetzungsregel, die eine beliebige Anzahl 11 Ziffern ermittelt und eine übersetzungsregel, die nur 11 Ziffern ermittelt, die mit + 1425 beginnen eingeschlossen haben, werden Sie beispielsweise sicher, dass die Regel, die eine beliebige Anzahl 11 Ziffern ermittelt sortierte *unten* die restriktivere ist Regel.

17. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.

18. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

    > [!NOTE]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Skype für Unternehmen](voice-route-config-changes.md) in der Betriebsdokumentation.

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Trunks mit medienumgehung in Skype für Business Server](configure-trunk-with-media-bypass.md)

[Definieren von Übersetzungsregeln](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

