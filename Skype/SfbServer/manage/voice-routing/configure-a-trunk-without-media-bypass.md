---
title: 'Skype for Business Server: Konfigurieren eines Trunks ohne Medienumgehung'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Konfigurieren eines Trunks mit aktivierter Medienumgehung '
ms.openlocfilehash: 906e5d793ba9b671d9a3d19b144ceac89b74428b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751734"
---
# <a name="skype-for-business-server---configure-a-trunk-without-media-bypass"></a>Skype for Business Server: Konfigurieren eines Trunks ohne Medienumgehung

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Wenn Sie einen Trunk mit aktivierter Medienumgehung konfigurieren möchten, lesen Sie die Informationen unter [Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server.](configure-a-trunk-with-media-bypass.md)

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen Trunk ohne Medienumgehung**

1. Öffnen Sie Skype für die Busines Server-Systemsteuerung.
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Standorttrunk:** Wählen Sie den Standort für diese Trunkkonfiguration in **"Standort auswählen"** aus, und klicken Sie dann auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. Dieser Trunk kann der Stammtrunk oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.
    > [!Note] 
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden. 

5. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
6. Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.
7. Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
8. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das **Kontrollkästchen Senden aktivieren über das Kontrollkästchen Gateway.**
9. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, der nicht von einem Skype for Business Server-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:
    - Klicken Sie auf **"Auswählen",** um einen oder mehrere Datensätze aus einer Liste aller PSTN-Verwendungsdatensätze auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.
    - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
            > [!Note] 
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden. 

        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf **"Auswählen",** um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        4. Klicken Sie auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:
        1. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf **"Auswählen",** um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        3. Klicken Sie auf **OK**.

    > [!Important] 
    > Es ist wichtig, PSTN-Verwendungsdatensätze gemäß dem Vermittlungsserverpeer zuzuordnen, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn der Vermittlungsserverpeer ein PSTN-Gateway oder ein Session Border Controller (SBC) ist, wird dringend empfohlen, die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zuzuordnen, der an ein PSTN-Ziel oder andere downstreame Systeme, die über Skype for Business Server verbunden sind, leitet. 

10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    > [!Important] 
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten. 

11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.
12. **Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.
13. **Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.
14. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird, erfolgt eine Umleitung zu einem anderen Trunk. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.
15. (Optional) Zuordnen und Konfigurieren von Übersetzungsregeln für **Anrufnummern** für den Trunk. Diese Übersetzungsregeln gelten für die Anrufnummer für ausgehende Anrufe.
    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.
    - Klicken Sie auf **"Auswählen",** um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP Bereitstellung verfügbar sind. Klicken Sie in "Übersetzungsregeln auswählen" auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **"OK".**
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server.](defining-translation-rules.md)
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Caution] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

17. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important] 
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer unter der restriktiveren Regel platziert werden. 

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013 in der Betriebsdokumentation. 
