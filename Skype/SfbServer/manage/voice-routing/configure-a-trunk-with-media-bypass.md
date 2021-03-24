---
title: Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server
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
ms.openlocfilehash: 91c1d495854a91e588c42fd22f6bd8e53fded7d8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103031"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server

Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit deaktivierter Medienumgehung finden Sie unter [Configure a trunk without media bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Ausgehende Skype for Business Server-Anrufrouten und Enterprise-VoIP müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway geroutet werden.

Es wird dringend empfohlen, die Medienumgehung zu aktivieren. Bevor Sie jedoch die Medienumgehung für einen SIP-Trunk aktivieren, vergewissern Sie sich, dass Ihr qualifizierter SIP-Trunkanbieter die Medienumgehung unterstützt und die Anforderungen für die erfolgreiche Aktivierung des Szenarios erfüllen kann. Insbesondere muss der Anbieter über die IP-Adressen von Servern im internen Netzwerk Ihrer Organisation verfügen. Wenn der Anbieter dieses Szenario nicht unterstützen kann, ist die Medienumgehung nicht erfolgreich. Weitere Informationen finden Sie unter [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> Die Medienumgehung funktioniert nicht mit jedem Public Switched Telephone Network (PSTN)-Gateway, ip-PBX und Session Border Controller (SBC). Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die auf der Seite [Telefonieinfrastruktur für Skype for Business Server aufgeführt](../../../SfbPartnerCertification/certification/infra-gateways.md) sind. 


Eine Trunkkonfiguration wie unten beschrieben enthält eine Gruppe von Parametern, die auf Trunks angewendet werden, denen diese Trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen Trunk mit Medienumgehung**

1. Öffnen Sie die Skype for Busines Server-Systemsteuerung.
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Standort trunk**: Wählen Sie unter Standort auswählen den Standort für diese Trunkkonfiguration **aus,** und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        - **Pool trunk**: Wählen Sie den Namen des Trunks aus, für den diese Trunkkonfiguration gilt. Bei diesem Trunk kann es sich um den Stamm trunk oder um alle zusätzlichen Trunks, die im Topologie-Generator definiert sind. Klicken **Sie unter Dienst auswählen** auf **OK**. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.
    
    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden. 

5. Geben Sie einen Wert unter **Maximal unterstützte frühe Dialogfelder an.** Dies ist die maximale Anzahl von gegabelten Antworten, die ein Public Switched Telephone Network (PSTN)-Gateway, eine IP-PBX-Anlage oder ein SBC (ITSP Session Border Controller) an eine EINLADUNG empfangen kann, die an den Vermittlungsserver gesendet wurde. Der Standardwert lautet 20.

    > [!NOTE] 
    > Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten. 

6. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
7. Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.

    > [!IMPORTANT]
    > Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen. Weitere Informationen finden Sie unter [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
9. Wenn der Trunk-Peer den Empfang von SIP -REFER-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen Senden aktivieren **verweisen auf das Gateway.** 

    > [!NOTE] 
    > Wenn Sie diese Option deaktivieren, während die Option **Medienumgehung aktivieren** ausgewählt ist, sind zusätzliche Einstellungen erforderlich. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet **Set-CsTrunkConfiguration** ausführen, um RTCP für aktive und gehaltene Anrufe zu deaktivieren, um geeignete Bedingungen für die Medienumgehung zu schaffen. Alternativ können Sie refer mithilfe der Anrufsteuerung eines Drittanbieters aktivieren auswählen, wenn übertragene Anrufe medienumgehungen werden sollen und das Gateway **SIP-REFER-Anforderungen** nicht unterstützt. 

10. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser Trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den Trunk angewendet, die nicht von einem Skype for Business Server-Endpunkt stammen. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:
    - Klicken Sie auf Auswählen, um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Bereitstellung verfügbaren PSTN-Enterprise-VoIP **auszuwählen.** Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.
    - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
            > [!NOTE] 
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden. 
        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf Auswählen, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        4. Klicken Sie auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:
        1. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf Auswählen, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP **auszuwählen.** Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        3. Klicken Sie auf **OK**.

    > [!Important]
    > Es ist wichtig, pstN-Verwendungsdatensätze gemäß dem Vermittlungsserver-Peer zuzuordnen, der dem zu konfigurierenden Trunk zugeordnet ist. Wenn es sich bei dem Vermittlungsserver-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die Trunkkonfiguration keinem PSTN-Verwendungsdatensatz zugeordnet ist, der zu einem PSTN-Ziel oder einem anderen downstream-System über Skype for Business Server verbunden ist. 

11. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server durchläuft die Liste von oben nach unten. 

12. **RtP-Latching** aktivieren sollte ausgewählt sein, um Die Umgehungsmedien für Clients hinter einer Netzwerkadressenübersetzung (Network Address Translation, NAT) oder Firewall und einem SBC zu aktivieren, der das Latching unterstützt.
13. **Der Anrufverlauf aktivieren** sollte ausgewählt sein, um das Senden von Anrufverlaufsinformationen an den Gateway-Peer des Vermittlungsservers zu ermöglichen.
14. Aktivieren Sie **die Weiterleitung von P-Asserted-Identity-Daten,** damit die P-Asserted-Identity (PAI)-Anruferinformationen zwischen dem Vermittlungsserver und der Gatewayseite (und umgekehrt) weitergeleitet werden können, wenn vorhanden.
15. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Eine Umleitung zu einem anderen Trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.
16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln gelten für die Rufnummer für ausgehende Anrufe.
    - Klicken Sie auf Auswählen, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP verfügbar **sind.** Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zum Definieren einer neuen Regel finden Sie unter [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Weitere Informationen finden Sie [unter Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen finden Sie [unter Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

17. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.
    - Klicken Sie auf Auswählen, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP verfügbar **sind.** Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Weitere Informationen zum Definieren einer neuen Regel finden Sie unter [Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Weitere Informationen finden Sie [unter Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Weitere Informationen finden Sie [unter Defining translation rules in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Warning] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

18. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    >[!Important] 
    > Skype for Business Server durchläuft die Übersetzungsregelliste von oben nach unten und verwendet die erste Regel, die der gewählten Nummer entspricht. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer *unter* der restriktiveren Regel platziert werden. 

19. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
20. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie [unter Publish pending changes to the voice routing configuration](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration). (BENÖTIGEN SIE EINEN NEUEN LINK?)

Nachdem Sie den Trunk konfiguriert haben, konfigurieren Sie die Medienumgehung weiterhin, indem Sie zwischen globalen Medienumgehungsoptionen auswählen, wie unter Bereitstellen der Medienumgehung [in Skype for Business Server beschrieben.](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md)