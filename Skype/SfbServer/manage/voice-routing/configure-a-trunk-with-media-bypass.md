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
description: 'Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. '
ms.openlocfilehash: 3628c0ea38c0692b313ee37ca7b836c159a5a2dd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817035"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Konfigurieren eines Trunks mit medienumgehung in Skype for Business Server

Führen Sie die folgenden Schritte aus, um einen Trunk mit aktivierter Medienumgehung zu konfigurieren. Informationen zum Konfigurieren eines Trunks mit deaktivierter medienumgehung finden Sie unter [Konfigurieren eines Trunks ohne medienumgehung in Skype for Business Server](configure-a-trunk-without-media-bypass.md). Die medienumgehung ist nützlich, wenn Sie die Anzahl der bereitgestellten Vermittlungsserver minimieren möchten. In der Regel wird ein Vermittlungs Server Pool an einem zentralen Standort bereitgestellt, und er steuert Gateways an Zweigstellen. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Skype for Business Server-ausgehende Anrufrouten und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort an das entsprechende Gateway weitergeleitet werden.

Es wird dringend empfohlen, die Medienumgehung zu aktivieren. Bevor Sie die Medienumgehung aber für einen SIP-Trunk aktivieren, müssen Sie sicherstellen, dass Ihr qualifizierter SIP-Trunkanbieter die Medienumgehung unterstützt und die Anforderungen für eine erfolgreiche Aktivierung des Szenarios erfüllt. Insbesondere muss der Anbieter über die IP-Adressen der Server im internen Netzwerk Ihrer Organisation verfügen. Wenn der Anbieter dieses Szenario nicht unterstützenkann, ist die medienumgehung nicht erfolgreich. Ausführliche Informationen finden Sie unter [Planen der medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> Die medienumgehung funktioniert nicht mit jedem PSTN-Gateway (Public Switched Telephone Network), IP-PBX und Session Border Controller (SBC). Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die auf der Seite [Telefonie-Infrastruktur für Skype for Business Server](../../../SfbPartnerCertification/certification/infra-gateways.md) aufgelistet sind. 


Eine Trunkkonfiguration wie die unten beschriebene gruppiert Parametersätze, die auf Trunks angewendet werden, denen die entsprechende Trunkkonfiguration zugewiesen ist. Eine bestimmte Trunkkonfiguration kann globale Reichweite haben (für alle Trunks, die keine spezifischere Standort- oder Poolkonfiguration haben) oder einen Standort oder Pool betreffen. Eine Trunkkonfiguration auf Poolebene wird verwendet, um eine bestimmte Trunkkonfiguration auf einen einzelnen Trunk anzuwenden.

**So konfigurieren Sie einen Trunk mit Medienumgehung**

1. Öffnen Sie die Skype for Business-Server-Systemsteuerung.
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **Trunkkonfiguration**.
3. Verwenden Sie auf der Seite **Trunkkonfiguration** eine der folgenden Methoden, um einen Trunk zu konfigurieren:
    - Doppelklicken Sie auf einen vorhandenen Trunk (z. B. den Trunk **Global**), um das Dialogfeld **Trunkkonfiguration bearbeiten** anzuzeigen.
    - Klicken Sie auf **Neu** und wählen Sie einen Bereich für die neue Trunkkonfiguration aus:
        - **Standorttrunk**: Wählen Sie den Standort für diese Trunkkonfiguration unter **Standort auswählen** aus und klicken Sie dann auf **OK**. Wenn bereits eine Trunkkonfiguration für einen Standort erstellt wurde, wird der Standort nicht unter **Standort auswählen** angezeigt.
        - **Pooltrunk**: Wählen Sie den Namen des Trunks aus, für den diese Trunkkonfiguration gilt. Dieser Stamm kann der Stamm Stamm oder alle zusätzlichen Trunks sein, die im Topologie-Generator definiert sind. Klicken Sie im Dialogfeld **Dienst auswählen** auf **OK**. Wenn bereits eine Trunkkonfiguration für einen bestimmten Trunk erstellt wurde, wird der Trunk nicht im Dialogfeld **Dienst auswählen** angezeigt.
    
    > [!NOTE]
    > Nachdem Sie den Bereich für die Trunkkonfiguration ausgewählt haben, kann dieser nicht mehr geändert werden. Das Feld **Name** ist bereits mit dem Namen des der Trunkkonfiguration zugeordneten Standorts oder Diensts ausgefüllt und kann nicht geändert werden. 

5. Geben Sie in **Höchstzahl unterstützter Earlydialoge** einen Wert ein. Dies ist die maximale Anzahl von gegabelten Antworten auf an den Vermittlungsserver gesendete INVITE-Anforderungen, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) beim Dienstanbieter empfangen kann. Der Standardwert lautet 20.

    > [!NOTE] 
    > Bevor Sie diesen Wert ändern, setzen Sie sich mit Ihrem Dienstanbieter oder Gerätehersteller in Verbindung, um genaue Informationen zu den Funktionen Ihres Systems zu erhalten. 

6. Wählen Sie unter **Unterstützte Verschlüsselungsstufe** eine der folgenden Optionen aus:
    - **Erforderlich**: Zum Schutz des Datenverkehrs zwischen dem Vermittlungsserver und dem Gateway oder der Nebenstellenanlage muss die SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) verwendet werden.
    - **Optional**: Die SRTP-Verschlüsselung wird verwendet, wenn der Dienstanbieter oder Gerätehersteller dieses Protokoll unterstützt.
    - **Nicht unterstützt**: Die SRTP-Verschlüsselung wird vom Dienstanbieter oder Gerätehersteller nicht unterstützt und daher nicht verwendet.
7. Aktivieren Sie das Kontrollkästchen **Medienumgehung aktivieren**, wenn Sie eine Umgehung des Vermittlungsservers zur Verarbeitung durch den Trunkpeer wünschen.

    > [!IMPORTANT]
    > Damit die Medienumgehung ordnungsgemäß funktioniert, müssen das PSTN-Gateway, die IP-Nebenstellenanlage oder der SBC beim Dienstanbieter bestimmte Funktionen unterstützen. Ausführliche Informationen finden Sie unter [Planen der medienumgehung in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Aktivieren Sie das Kontrollkästchen **Zentralisierte Medienverarbeitung**, wenn ein bekannter Medienendpunkt vorhanden ist (beispielsweise ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse aufweist wie der signalgebende Endpunkt). Deaktivieren Sie dieses Kontrollkästchen, wenn der Trunk über keinen bekannten Medienendpunkt verfügt.
9. Wenn der trunk-Peer das Empfangen von SIP-Refer-Anforderungen vom Vermittlungs Server unterstützt, aktivieren Sie das Kontrollkästchen **senden verweisen auf das Gateway** . 

    > [!NOTE] 
    > Wenn Sie diese Option deaktivieren, während die Option **Medienumgehung aktivieren** ausgewählt ist, sind zusätzliche Einstellungen erforderlich. Wenn der Trunkpeer den Empfang von SIP REFER-Anforderungen vom Vermittlungsserver nicht unterstützt und die Medienumgehung aktiviert ist, müssen Sie außerdem das Cmdlet **Set-CsTrunkConfiguration** zur Deaktivierung von RTCP für aktive und gehaltene Anrufe ausführen, um geeignete Bedingungen für die Medienumgehung zu schaffen. Alternativ können Sie **Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren** auswählen, wenn Sie möchten, dass für übertragene Anrufe eine Medienumgehung stattfinden soll, und das Gateway keine SIP REFER-Anforderungen unterstützt. 

10. (Optional) Für die Aktivierung der Weiterleitung zwischen Trunks ordnen Sie dieser Trunkkonfiguration PSTN-Verwendungsdatensätze zu und konfigurieren Sie diese. Die PSTN-Nutzungen, die dieser trunk-Konfiguration zugeordnet sind, werden für alle eingehenden Anrufe über den trunk übernommen, der nicht von einem Skype for Business Server-Endpunkt stammt. Für die Verwaltung der einer Trunkkonfiguration zugeordneten PSTN-Verwendungsdatensätze können Sie eines der folgenden Verfahren nutzen:
    - Wenn Sie einen oder mehrere Datensätze aus einer Liste aller für Ihre Enterprise-VoIP-Bereitstellung verfügbaren PSTN-Verwendungsdaten Sätze auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Datensätze, die Sie dieser Trunkkonfiguration zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Markieren Sie einen Datensatz und klicken Sie auf **Entfernen**, um einen PSTN-Verwendungsdatensatz aus der Trunkkonfiguration zu entfernen.
    - Führen Sie die folgenden Schritte aus, um einen neuen PSTN-Verwendungsdatensatz zu definieren und dieser Trunkkonfiguration zuzuordnen:
        1. Klicken Sie auf **Neu**.
        2. Geben Sie im Feld **Name** einen eindeutigen beschreibenden Namen für den Datensatz an.
            > [!NOTE] 
            > Der Name des PSTN-Verwendungseintrags muss innerhalb der Enterprise-VoIP-Bereitstellung eindeutig sein. Nach dem Speichern des Eintrags kann das Feld **Name** nicht mehr bearbeitet werden. 
        3. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            - Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. 
            - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. 
        4. Klicken Sie anschließend auf **OK**.
    - Führen Sie die folgenden Schritte aus, um einen PSTN-Verwendungsdatensatz zu bearbeiten, der dieser Trunkkonfiguration bereits zugeordnet ist:
        1. Wählen Sie den PSTN-Verwendungsdatensatz aus, den Sie bearbeiten möchten, und klicken Sie auf **Details anzeigen**.
        2. Verwenden Sie eine der folgenden Methoden, um Routen für diesen PSTN-Verwendungsdatensatz zuzuordnen und zu konfigurieren:
            - Wenn Sie eine oder mehrere Routen aus der Liste aller verfügbaren Routen in Ihrer Enterprise-VoIP-Bereitstellung auswählen möchten, klicken Sie auf **auswählen**. Markieren Sie die Routen, die Sie dem PSTN-Verwendungsdatensatz zuordnen möchten, und klicken Sie dann auf **OK**. 
            - Zum Entfernen einer Route aus dem PSTN-Verwendungsdatensatz wählen Sie die Route aus und klicken Sie auf **Entfernen**.
            - Zur Definition einer neuen Route und ihrer Zuordnung zu diesem PSTN-Verwendungsdatensatz klicken Sie auf **Neu**. 
            - Zum Bearbeiten einer Route, die diesem PSTN-Verwendungsdatensatz zugeordnet wurde, wählen Sie die Route aus und klicken Sie auf **Details anzeigen**. 
        3. Klicken Sie anschließend auf **OK**.

    > [!Important]
    > Es ist wichtig, die PSTN-Verwendungsdaten Sätze entsprechend dem Vermittlungs Server-Peer zuzuordnen, der dem zu konfigurierenden trunk zugeordnet ist. Wenn es sich bei dem Vermittlungs Server-Peer um ein PSTN-Gateway oder einen Session Border Controller (SBC) handelt, wird dringend empfohlen, dass die trunk-Konfiguration keinem PSTN-Verwendungsdaten Satz zugeordnet ist, der zu einem PSTN-Ziel oder zu anderen nachgeschalteten, über Skype verbundenen Systemen weitergeleitet wird. für Business Server. 

11. Ordnen Sie die PSTN-Verwendungsdatensätze zur Erzielung einer optimalen Leistung an. Wenn Sie die Position eines Datensatzes in der Liste ändern möchten, wählen Sie den PSTN-Verwendungsdatensatz aus und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    > [!Important]
    > Die Reihenfolge, in der PSTN-Verwendungsdatensätze in der Trunkkonfiguration aufgeführt werden, ist maßgeblich. Skype for Business Server durchläuft die Liste von oben nach unten. 

12. Aktivieren Sie **RTP-Verriegelung aktivieren**, um Umgehungsmedien für Clients hinter einer NAT oder Firewall und einem SBC, der die Verriegelung unterstützt, zu aktivieren.
13. **Aktivieren Sie das Weiterleitungs Anrufprotokoll** , um das Senden von Anrufverlaufs Informationen an den Gateway-Peer des Vermittlungsservers zu ermöglichen.
14. **Enable Forward p-asserted – Identitätsdaten** sollten ausgewählt werden, damit die p-asserted-Identity (Pai)-Anruf Absenderinformationen zwischen dem Vermittlungs Server und dem Gateway (und umgekehrt) weitergeleitet werden, wenn vorhanden.
15. **Failovertimer für Ausgangsrouting aktivieren** sollte aktiviert sein, um ein schnelles Failover zu aktivieren. Das diesem Trunk zugeordnete Gateway kann innerhalb von zehn Sekunden eine Benachrichtigung ausgeben, dass ein ausgehender Anruf verarbeitet wird. Das erneute Routing zu einem anderen trunk erfolgt, wenn diese Benachrichtigung nicht vom Vermittlungs Server empfangen wird. In Netzwerken, in denen die Latenz die Antwortzeit möglicherweise verzögert oder in denen das Gateway für die Antwort mehr als zehn Sekunden benötigt, sollte das schnelle Failover deaktiviert werden.
16. (Optional) Zuordnen und Konfigurieren von **Übersetzungsregeln für die wählende Nummer** für den Trunk. Diese Übersetzungsregeln gelten für die Rufnummer für ausgehende Anrufe.
    - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.
    > [!Warning]
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

17. (Optional) Ordnen Sie **Übersetzungsregeln für die gewählte Nummer** für den Trunk zu und konfigurieren Sie diese. Die Übersetzungsregeln gelten für die angerufene Nummer in einem ausgehenden Anruf.
    - Wenn Sie eine oder mehrere Regeln aus einer Liste aller Übersetzungsregeln auswählen möchten, die in Ihrer Enterprise-VoIP-Bereitstellung verfügbar sind, klicken Sie auf **auswählen**. Klicken Sie im Abschnitt **Übersetzungsregeln auswählen** auf die Regeln, die Sie dem Trunk zuordnen möchten, und klicken Sie anschließend auf **OK**.
    - Klicken Sie auf **Neu**, um eine neue Übersetzungsregel zu definieren und dem Trunk zuzuordnen. Details zum Definieren einer neuen Regel finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Klicken Sie auf den Regelnamen und anschließend auf **Details anzeigen**, um eine Übersetzungsregel zu bearbeiten, die dem Trunk bereits zugeordnet ist. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine vorhandene Übersetzungsregel als Ausgangspunkt für die Definition einer neuen Regel verwenden möchten, klicken Sie auf den Regelnamen, auf **Kopieren** und anschließend auf **Einfügen**. Ausführliche Informationen finden Sie unter [Definieren von Übersetzungsregeln in Skype for Business Server](defining-translation-rules.md).
    - Wenn Sie eine Übersetzungsregel vom Trunk entfernen möchten, markieren Sie den Regelnamen und klicken Sie auf **Entfernen**.

    > [!Warning] 
    > Ordnen Sie einem Trunk keine Übersetzungsregeln zu, wenn Sie Übersetzungsregeln für den zugeordneten Trunkpeer konfiguriert haben, da zwischen den beiden Regeln Konflikte auftreten könnten. 

18. Stellen Sie sicher, dass die Übersetzungsregeln für den Trunk in der richtigen Reihenfolge angeordnet sind. Wenn Sie die Position einer Regel in der Liste ändern möchten, markieren Sie den Regelnamen und klicken Sie auf den nach oben oder nach unten weisenden Pfeil.

    >[!Important] 
    > Skype for Business Server durchsucht die Übersetzungsregel Liste von oben nach unten und verwendet die erste Regel, die mit der gewählten Nummer übereinstimmt. Wenn Sie einen Trunk so konfigurieren, dass eine gewählte Nummer mit mehreren Übersetzungsregeln übereinstimmen kann, müssen Sie sicherstellen, dass die stärker einschränkenden Regeln über den weniger einschränkenden Regeln angeordnet sind. Wenn Sie beispielsweise eine Übersetzungsregel verwenden, die mit einer beliebigen elfstelligen Nummer übereinstimmt, und eine andere Übersetzungsregel auf elfstellige Nummern zutrifft, die mit +1425 beginnen, muss die Regel für eine beliebige elfstellige Nummer *unter* der restriktiveren Regel platziert werden. 

19. Nachdem Sie die Trunkkonfiguration abgeschlossen haben, klicken Sie auf **OK**.
20. Klicken Sie auf der Seite **Trunkkonfiguration** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 

    > [!Note]
    > Jedes Mal, wenn Sie eine Trunkkonfiguration erstellen oder ändern, müssen Sie den Befehl **Commit für alle Elemente ausführen** ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). (benötigen Sie einen neuen Link?)

Nachdem Sie den trunk konfiguriert haben, fahren Sie mit dem Konfigurieren der medienumgehung fort, indem Sie zwischen globalen Medien Umgehungs Optionen wählen, wie unter [Bereitstellen von medienumgehung in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md)beschrieben.

