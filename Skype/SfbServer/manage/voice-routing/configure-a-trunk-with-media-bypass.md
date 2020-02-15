---
title: Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Führen Sie die folgenden Schritte aus, um einen trunk mit aktivierter medienumgehung zu konfigurieren. '
ms.openlocfilehash: 293c39884c1ef6c8e82521b3fd248ae6bbc18d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009548"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server

Führen Sie die folgenden Schritte aus, um einen trunk mit aktivierter medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit deaktivierter medienumgehung finden Sie unter [Configure a trunk without Media Bypass in Skype for Business Server](configure-a-trunk-without-media-bypass.md). Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Skype for Business Server ausgehenden Anrufrouten und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.

Es wird dringend empfohlen, die medienumgehung zu aktivieren. Bevor Sie jedoch die medienumgehung für einen SIP-Trunk aktivieren, müssen Sie sicherstellen, dass der qualifizierte SIP-Trunk Anbieter die medienumgehung unterstützt und die Anforderungen für die erfolgreiche Aktivierung des Szenarios erfüllen kann. Insbesondere muss der Anbieter über die IP-Adressen von Servern im internen Netzwerk Ihrer Organisation verfügen. Wenn der Anbieter dieses Szenario nicht unterstützen kann, ist die Medienumgehung nicht erfolgreich. Ausführliche Informationen finden Sie unter [Plan for Media Bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> Die medienumgehung kann nicht mit jedem PSTN-Gateway (Public Switched Telephone Network), IP-PBX-Gerät und einem SBC (Session Border Controller) zusammenarbeiten. Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die auf der Seite [Telefonie-Infrastruktur für Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) aufgeführt sind. 


Eine trunkkonfiguration wie unten beschrieben gruppiert eine Gruppe von Parametern, die auf Trunks angewendet werden, denen diese trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann auf globale Ebene (für alle Trunks, die keine speziellere Standort- oder Poolkonfiguration haben) oder für einen Standort oder Pool festgelegt werden. Die Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen trunk mit medienumgehung**

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu**, und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Website trunk**: Wählen Sie den Standort für diese trunkkonfiguration aus Standort **auswählen**aus, und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt. Diese Trunkkonfiguration wird auf alle Trunks am Standort angewendet.
        - **Pool trunk**: Wählen Sie den Namen des Trunks aus, für den diese trunkkonfiguration gilt. Bei diesem trunk kann es sich um den Stamm trunk oder um zusätzliche Trunks handeln, die im Topologie-Generator definiert sind. Klicken Sie unter **Dienst auswählen**auf **OK**. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, erscheint dieser Trunk nicht unter **Dienst auswählen**.
    
    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** wird mit dem Namen der Trunkkonfiguration vorausgefüllt, der dem Standort oder Dienst zugeordnet ist, und kann nicht geändert werden. 

5. Geben Sie einen Wert in **maximal unterstützten frühen Dialogfeldern**an. Hierbei handelt es sich um die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway (Public Switched Telephone Network), eine IP-Nebenstellenanlage oder einen ITSP-Sitzungs Rahmen Controller (SBC) an eine Einladung empfangen kann, die an den Vermittlungsserver gesendet wurde. Der Standardwert lautet 20.

    > [!NOTE] 
    > Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten. 

6. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage (Private Branch Exchange, PBX) muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
7. Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.

    > [!IMPORTANT]
    > Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen. Ausführliche Informationen finden Sie unter [Plan for Media Bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Aktivieren Sie das Kontrollkästchen **Zentrale Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
9. Wenn der trunk Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungsserver unterstützt, aktivieren Sie das Kontrollkästchen **Senden von referieren auf das Gateway aktivieren** . 

    > [!NOTE] 
    > Wenn Sie diese Option deaktivieren, während die Option **Medienumgehung aktivieren** ausgewählt ist, sind zusätzliche Einstellungen erforderlich. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet **Set-CsTrunkConfiguration** ausführen, um RTCP für aktive und gehaltene Anrufe zu deaktivieren, um geeignete Bedingungen für die Medienumgehung zu schaffen. Alternativ können Sie die Option **Refer mithilfe von Drittanbieter Anrufsteuerung aktivieren** auswählen, wenn die Übertragung von Anrufen auf Medien umgangen werden soll und das Gateway SIP-Refer-Anforderungen nicht unterstützt. 

10. (Optional) Um Routing zwischen Trunks zu ermöglichen, können Sie dieser Trunkkonfiguration PSTN-Verwendungseinträge zuordnen und konfigurieren. Die dieser trunkkonfiguration zugeordneten PSTN-Verwendungen werden für alle eingehenden Anrufe über den trunk übernommen, der nicht von einem Skype for Business Server-Endpunkt stammt. Verwenden Sie eine der folgenden Methoden, um die einer Trunkkonfiguration zugeordneten PSTN-Verwendungseinträge zu verwalten:
    - Klicken Sie auf **auswählen**, um einen oder mehrere Datensätze aus einer Liste aller in Ihrer Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungseinträge auszuwählen. Markieren Sie die Einträge, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf **OK**.
    - Markieren Sie einen Eintrag, und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungseintrag aus dieser Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungseintrag zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Eintrag ein.
            > [!NOTE] 
            > Der Name des PSTN-Verwendungsdatensatzes muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Datensatzes kann das Feld **Name** nicht mehr bearbeitet werden. 
        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        4. Klicken Sie auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungseintrag zu bearbeiten, der bereits dieser Trunkkonfiguration zugeordnet ist:
        1. Markieren Sie den PSTN-Verwendungseintrag, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungseintrag zuzuordnen und zu konfigurieren:
            - Klicken Sie auf **auswählen**, um eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auszuwählen. Markieren Sie die Routen, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie dann auf**OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungseintrag markieren Sie die Route, und klicken Sie auf **Entfernen**.
            - Klicken Sie auf **Neu**, um eine neue Route zu definieren und sie diesem PSTN-Verwendungseintrag zuzuordnen. 
            - Markieren Sie die Route, und klicken Sie auf **Details anzeigen**, um eine Route zu bearbeiten, die dem PSTN-Verwendungseintrag zugeordnet ist. 
        3. Klicken Sie auf **OK**.

    > [!Important]
    > Es ist wichtig, PSTN-Verwendungsdaten Sätze gemäß dem Vermittlungsserver Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist. Wenn es sich bei dem Vermittlungsserver Peer um ein PSTN-Gateway oder einen SBC (Session Border Controller) handelt, wird dringend empfohlen, dass die trunkkonfiguration keinem PSTN-Verwendungs Eintrag zugeordnet ist, der an ein PSTN-Ziel oder andere nachgeschaltete Systeme weitergeleitet wird, die über Skype verbunden sind. for Business Server. 

11. Ordnen Sie die PSTN-Verwendungseinträge zur Erzielung optimaler Leistung an. Wenn Sie die Position eines Eintrags in der Liste ändern möchten, markieren Sie den PSTN-Verwendungseintrag, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important]
    > Die Reihenfolge, in der PSTN-Verwendungseinträge in der Trunkkonfiguration aufgeführt werden, ist relevant. Skype for Business Server die Liste von oben nach unten durchlaufen. 

12. **Aktivieren Sie RTP-Latching** , um die Umgehung von Medien für Clients hinter einer Netzwerkadressübersetzung (Network Address Translation, NAT) oder einer Firewall und einen SBC zu aktivieren, der das Latching unterstützt.
13. **Enable Forward Call History** sollte ausgewählt sein, um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsserver zu ermöglichen.
14. **Enable Forward p-asserted-Identity Data** sollte ausgewählt sein, damit die p-asserted-Identity (Pai)-Anruf Absenderinformationen zwischen der Vermittlungsserver Seite und der Gatewayseite (und umgekehrt) weitergeleitet werden können, sofern vorhanden.
15. **Failovertimer für Ausgangsrouting aktivieren** sollte ausgewählt sein, um ein schnelleres Failover zu ermöglichen. Das diesem Trunk zugeordnete Gateway kann innerhalb von 10 Sekunden eine Benachrichtigung senden, dass ein ausgehender Anruf verarbeitet wird. Das erneute Routing an einen anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungsserver empfangen wird. In Netzwerken, in denen Latenz die Reaktionszeit verzögern kann oder das Gateway länger als 10 Sekunden benötigt, um zu antworten, sollte das schnelle Failover deaktiviert werden.
16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln gelten für die Anrufnummer für ausgehende Anrufe.
    - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.
    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

17. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die gewählte Nummer** für den Trunk. Diese Übersetzungsregeln werden bei ausgehenden Anrufen auf die gewählte Nummer angewendet.
    - Klicken Sie auf **auswählen**, um eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auszuwählen, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Ausführliche Informationen zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die bereits dem Trunk zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Um eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel zu verwenden, klicken Sie auf den Regelnamen, klicken Sie auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen, und klicken Sie auf **Entfernen**.

    > [!Warning] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den zwei Regeln Konflikte auftreten können. 

18. Stellen Sie sicher, dass die Übersetzungsregeln des Trunks in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen, und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    >[!Important] 
    > Skype for Business Server durchläuft die Liste der Übersetzungsregeln von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehr als einer Übersetzungsregel übereinstimmen kann, müssen Sie sicherstellen, dass die einschränkenderen Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer *unter* der restriktiveren Regel platziert werden. 

19. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
20. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit**, und klicken Sie anschließend auf **Commit für alle**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). (neuer Link erforderlich?)

Nachdem Sie den trunk konfiguriert haben, fahren Sie mit dem Konfigurieren der medienumgehung fort, indem Sie zwischen den Optionen für die globale medienumgehung auswählen, wie unter [Deploy Media Bypass in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md)beschrieben.

