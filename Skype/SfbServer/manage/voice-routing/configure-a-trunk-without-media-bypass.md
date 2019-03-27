---
title: Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. '
ms.openlocfilehash: 623de0439e6c6297808e54eb2ae050aa95f6533d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881932"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks ohne medienumgehung in Skype für Business Server

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen Trunk mit medienumgehung konfigurieren möchten, finden Sie unter [Konfigurieren eines Trunks mit Medien in Skype für Business Server umgehen](configure-a-trunk-with-media-bypass.md).

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globaler Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen Trunk ohne Medienumgehung**

1. Öffnen von Skype Business Server-Systemsteuerung.
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu** und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Website-Trunk**: Wählen Sie die Website für dieser trunkkonfiguration im **Dialogfeld Standort auswählen**, und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. In diesem Trunk kann der stammtrunk oder alle zusätzlichen Trunks im Topologie-Generator definiert sein. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird dieser Trunk nicht unter **Dienst auswählen** angezeigt.
    > [!Note] 
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** ist bereits mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts ausgefüllt und kann nicht geändert werden. 

5. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
6. Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.
7. Aktivieren Sie das Kontrollkästchen **zentrale Media verarbeiten** , wenn es eine bekannte Media Endpunkt (beispielsweise ein Gateway public switched Telephone Network (Telefonfestnetz PSTN ist), bei denen die Beendigung Media die dieselbe IP-Adresse als die Signalisierung Beendigung hat). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
8. Wenn Sie der trunkpeer das Empfangen von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden der Weiterleitung an das Gateway aktivieren** .
9. (Optional) Zur Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu und konfigurieren Sie diese. Dieser trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, die nicht von einem Skype für Business Server Endpunkt stammt. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:
    - Um einen oder mehrere Datensätze aus einer Liste aller PSTN-verwendungsdatensätzen in Ihrer Bereitstellung von Enterprise-VoIP verfügbar auszuwählen, klicken Sie auf **auswählen**. Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Markieren Sie einen Datensatz und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.
            > [!Note] 
            > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden. 

        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            - Um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Bereitstellung von Enterprise-VoIP ausgewählt haben, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. 
            - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. 
        4. Klicken Sie anschließend auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:
        1. Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            - Um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Bereitstellung von Enterprise-VoIP ausgewählt haben, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. 
            - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. 
        3. Klicken Sie anschließend auf **OK**.

    > [!Important] 
    > Es ist wichtig, um PSTN-verwendungsdatensätzen entsprechend der Vermittlungsserver Peer zuzuordnen, die den konfigurierten Trunk zugeordnet ist. Wenn der Vermittlungsserver Peer ein PSTN-Gateway oder ein Session Border Controller (SBC) ist, wird dringend empfohlen, dass die trunkkonfiguration nicht mit einem PSTN-Datensatz verknüpft ist, die über Skype-Routen für ein PSTN-Ziel oder eine beliebige andere downstream-Systemen verbunden für Business Server. 

10. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung einer optimalen Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    > [!Important] 
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Skype für Business Server durchläuft die Liste von oben nach unten. 

11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.
12. **Weiterleitung des Anrufverlaufs aktivieren** sollte ausgewählt sein, damit das Senden von anrufverlaufsinformationen an dem gatewaypeer des Vermittlungsservers.
13. **Weiterleiten von P-Asserted-Identity-Daten aktivieren** sollte ausgewählt sein, damit PAI Informationen zwischen der vermittlungsserverseite und der gatewayseite weitergeleitet werden (und umgekehrt), bei der Vorstellung.
14. **Failovertimer für Ausgangsrouting aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Weiterleitung an einen anderen Trunk auftreten, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.
15. (Optional) Zuordnen und **Konfigurieren von Übersetzungsregeln** für den Trunk. Diese Übersetzungsregeln gelten für die Nummer des Anrufers für ausgehende Anrufe.
    - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln auszuwählen, die in der Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Weitere Informationen hierzu finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen hierzu finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

16. (Optional) Ordnen Sie **Übersetzungsregeln für die gewählte Nummer** für den Trunk zu und konfigurieren Sie diese. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf.
    - Um eine oder mehrere Regeln aus einer Liste mit allen Übersetzungsregeln auszuwählen, die in der Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie in Übersetzungsregeln auswählen auf die Regeln, die dem Trunk zugeordnet werden soll, und klicken Sie dann auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Weitere Informationen hierzu finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen hierzu finden Sie unter [Definieren von Übersetzungsregeln in Skype für Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

    > [!Caution] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

17. Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important] 
    > Skype für Business Server durchläuft die Liste der Übersetzung von oben nach unten und verwendet die erste Regel, die mit die gewählte Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehreren Übersetzungsregeln übereinstimmen kann, müssen Sie sicherstellen, dass die stärker einschränkenden Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer unter der restriktiveren Regel platziert werden. 

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013 in der Betriebsdokumentation. 
