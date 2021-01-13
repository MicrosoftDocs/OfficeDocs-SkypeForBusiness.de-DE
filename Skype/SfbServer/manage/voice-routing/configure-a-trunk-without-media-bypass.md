---
title: Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server
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
description: 'Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. '
ms.openlocfilehash: 340f4b7e24b2734d3b8c3284b4f82044f65beea0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806455"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks ohne Medienumgehung in Skype for Business Server

Führen Sie die folgenden Schritte aus, um einen Trunk mit deaktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit aktivierter Medienumgehung finden Sie unter "Konfigurieren eines Trunks mit Medienumgehung [in Skype for Business Server".](configure-a-trunk-with-media-bypass.md)

Eine Trunkkonfiguration ist eine Gruppe von Parametern, die auf Trunks angewendet werden, die dieser Trunkkonfiguration zugewiesen sind. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen Trunk ohne Medienumgehung**

1. Öffnen Sie die Skype for Busines Server-Systemsteuerung.
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
4. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Standort-Trunk:** Wählen Sie den Standort für diese Trunkkonfiguration in **"Standort** auswählen" aus, und klicken Sie dann auf **"OK".** Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        - **Pooltrunk**: Wählen Sie unter **Dienst auswählen** den Namen des Trunks aus, auf den diese Trunkkonfiguration angewendet wird, und klicken Sie auf **OK**. Dieser Trunk kann der Stamm trunk oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.
    > [!Note] 
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden. 

5. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
6. Stellen Sie sicher, dass das Kontrollkästchen **Medienumgehung aktivieren** deaktiviert ist.
7. Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
8. Wenn der Trunk-Peer den Empfang von SIP -REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen "Senden aktivieren" im **Gateway.**
9. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, der nicht von einem Skype for Business Server-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:
    - Klicken Sie auf "Auswählen", um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Bereitstellung verfügbaren ENTERPRISE-VOIP **auszuwählen.** Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.
    - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
            > [!Note] 
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden. 

        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf "Auswählen", um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        4. Klicken Sie auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:
        1. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf "Auswählen", um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        3. Klicken Sie auf **OK**.

    > [!Important] 
    > Es ist wichtig, die PstN-Verwendungseinträge entsprechend dem Vermittlungsserver-Peer zuzuordnen, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn es sich bei dem Vermittlungsserver-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zugeordnet ist, der an ein PstN-Ziel oder andere nachgelagerte Systeme, die über Skype for Business Server verbunden sind, weiterroutet. 

10. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.
    > [!Important] 
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten. 

11. **RTP-Verriegelung aktivieren** sollte ausgewählt sein, um die Medienumgehung für Clients hinter einer Netzwerkadressenübersetzung (NAT) oder Firewall und einen SBC, der Verriegelung unterstützt, zu aktivieren.
12. **Die Option "Anrufverlauf weiterleiten"** sollte aktiviert sein, um das Senden von Anrufverlaufsinformationen an den Gateway-Peer des Vermittlungsservers zu aktivieren.
13. **Die Weiterleitung von P-Asserted-Identity-Daten** sollte aktiviert werden, um die Weiterleitung von Informationen zum Ermittler von PAI zwischen dem Vermittlungsserver und gatewayseitig (und umgekehrt) zu ermöglichen, wenn vorhanden.
14. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Das erneute Umleitung an einen anderen Trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.
15. (Optional) Ordnen Sie **Übersetzungsregeln für die Telefonnummer für den** Trunk zu, und konfigurieren Sie diese. Diese Übersetzungsregeln gelten für die Anrufnummer für ausgehende Anrufe.
    - Klicken Sie auf "Auswählen", um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP **verfügbar sind.** Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Weitere Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.
    - Klicken Sie auf "Auswählen", um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP **verfügbar sind.** Klicken Sie in "Übersetzungsregeln auswählen" auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie dann auf **"OK".**
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Weitere Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Caution] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

17. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important] 
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer unter der restriktiveren Regel platziert werden. 

18. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
19. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter Publish pending changes to the voice routing configuration in Lync Server 2013 in the Operations documentation. 
