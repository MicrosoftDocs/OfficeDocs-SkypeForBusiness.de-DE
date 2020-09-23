---
title: Allgemeine Front-End-Einstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Um die Einstellungen für eine vorhandene Front-End-Pool oder Standard Edition-Server zu bearbeiten, werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: 6f66fadbc722f59bdc7bcb54b149bf05fa322afb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215506"
---
# <a name="front-end-general-settings-expander"></a>Allgemeine Front-End-Einstellungen – Erweiterung

Um die Einstellungen für eine vorhandene Front-End-Pool oder Standard Edition-Server zu bearbeiten, werden die folgenden Abschnitte angezeigt:

- Allgemeine Einstellungen

- Ausfallsicherheitseinstellungen

- Webdiensteinstellungen

- Vermittlungsservereinstellungen

## <a name="front-end-pool"></a>Front-End-Pool

Für einen Front-End-Pool können Sie allgemeine Einstellungen sowie Einstellungen zu Ausfallsicherheit, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Front-End-Pool finden Sie unter [Deploying Mediation Servers and Definition Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**. Bearbeiten Sie den vollqualifizierten Domänennamen des Pools, um ihn zu ändern.

- **Hardware-Lastenausgleichs Überwachung-Port aktivieren**. Aktivieren Sie das Kontrollkästchen, und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status der Poolserver verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie mit diesem Pool verbinden möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**: Schließt Audio, Video und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie Einwahlkonferenzen (PSTN) auswählen. Im Unterabschnitt zu Vermittlungsservereinstellungen weiter unten in diesem Abschnitt geben Sie ein PSTN-Gateway an und definieren es.

  - **Enterprise-VoIP**. Aktiviert interne Voice over IP-Anrufe für qualifizierte Mobiltelefone und Geräte und Skype for Business Clients. Zum Aktivieren externer Anruffunktionen müssen Sie einen Vermittlungsserver einschließen. Ausführliche Informationen finden Sie unter "Vermittlungsserver" weiter unten in diesem Thema.

- Bearbeiten Sie in **Zuordnungen** Folgendes, oder geben Sie es an:

  - **SQL-Speicher**. Ändern Sie eine vorhandene SQL Server Datenbank, oder erstellen Sie eine neue SQL Server basierte Datenbank, in der die Front-End-Pool Datenbanken gespeichert sind. Sie können eine neue Instanz von SQL Server aus der Liste auswählen oder einen neuen Eintrag erstellen, indem Sie auf **neu**klicken.

    Wählen Sie **SQL Server Speicherspiegelung aktivieren**aus, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

    Wählen Sie **SQL Server Spiegelungs Zeugen verwenden aus, um das automatische Failover zu aktivieren** , um einen Server auszuwählen, der als Spiegelungs Zeuge verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

  - **Dateifreigabe**. Ändern Sie den vom Front-End-Pool verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**. Ordnen Sie dem Front-End-Pool einen Archivierungsserver Speicher zu. Sie können aus einer bereits definierten Archivierungs SQL Server Speicher auswählen, indem Sie den Server aus der Liste auswählen oder auf **neu** klicken, um einen neuen Archivierungsserver anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

    Wählen Sie **SQL Server Speicherspiegelung aktivieren**aus, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

    Wählen Sie **SQL Server Spiegelungs Zeugen verwenden aus, um das automatische Failover zu aktivieren** , um einen Server auszuwählen, der als Spiegelungs Zeuge verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

  - **Überwachung (KDS-und QoE-Metriken)**. Wählen Sie diese Option aus, um dem Front-End-Pool einen Überwachungs SQL Server Speicher zuzuordnen. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

    Wählen Sie **SQL Server Speicherspiegelung aktivieren**aus, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

    Wählen Sie **SQL Server Spiegelungs Zeugen verwenden aus, um das automatische Failover zu aktivieren** , um einen Server auszuwählen, der als Spiegelungs Zeuge verwendet werden soll. Klicken Sie auf **neu** , um einen neuen SQL Server Speicher zu erstellen.

  - **Zuordnen von Edgepool (für Medienkomponenten)**. Ordnen Sie dem Front-End-Pool einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

  - **Verknüpfen eines Pools mit einem Office-webapps-Server**. Wählen Sie diese Option aus, um dem Front-End-Pool einen Office-webapps-Server zuzuordnen. Wählen Sie einen vorhandenen Server aus der Liste aus, oder klicken Sie auf **neu** , um einen neuen Office-webapps-Server zu erstellen.

### <a name="resiliency"></a>Flexibilität

Ausfallsicherheit bietet Notfallwiederherstellung und hohe Verfügbarkeit für den Pool. Wenn der primäre Server ausfällt, kann der Sicherungsserver durch die Bereitstellung einer Sicherung übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Je nachdem, welche Systeme mit dem primären Server ausgefallen sind, kann die Funktionalität für Benutzer eingeschränkt sein.

Wählen Sie in der Liste die Front-End-Pool oder Standard Edition-Server aus, die als Sicherungsserver für den Pool fungieren sollen. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Durch Aktivieren der Failover-und Fallback-Zeiteinstellungen (in Sekunden angegeben) wird die automatische Erkennung eines ausgefallenen Servers und eine Fallback-Zeit aktiviert, um die automatische Ermittlung der primären Sicherung zu ermöglichen.

> [!IMPORTANT]
> Beim Definieren der Fehlererkennung und des Fall Back Intervalls sollten Sie darauf achten, dass Sie nicht ein Intervall eingeben, das dazu führt, dass Failover und Fallback auftreten, wenn der Server für einen kurzen Zeitraum nicht antwortet. Es ist möglich, dass der primäre Server möglicherweise nicht für kurze Zeiträume reagiert, je nachdem, ob der Pool oder die Server geladen werden. Die Standardwerte für Failover und Fallback sind 300 Sekunden und 600 Sekunden für Pool-zu-Pool-oder Pool-Standard Edition-Server. Im Falle einer Survivable Branch Appliance oder eines Survivable Branch Servers in einer Website zu einem Pool oder Standard Edition-Server sind die Standardwerte 120 Sekunden für Failover und 240 Sekunden für Fallback.

> [!CAUTION]
> Der Minimalwert für das **Failover-Intervall** sollte nicht niedriger als 90 Sekunden festgelegt werden. Wenn Sie den Wert auf weniger als 90 Sekunden festlegen, wird der Wert von 90 Sekunden verwendet. Die zwischen Cluster-Pingzeit beträgt 30 Sekunden, und eine Einstellung niedriger als 90 Sekunden kann dazu führen, dass die primären und die Sicherungsserver auf-und ablaufen, was zu unerwünschten Auswirkungen auf die Produktion führt, da die Server versuchen, den lebensfähigen Status des anderen zu beheben. In weniger als 90 Sekunden kann nicht genug Zeit festgestellt werden, um zu ermitteln, ob der primäre Server tatsächlich nicht verfügbar ist oder nicht.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Front-End-Pool müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Geben Sie in **Interne Webdienste** Folgendes an:

> [!CAUTION]
> Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für eine andere Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für alle Directors oder Directorpool definiert ist, von allen anderen Director-oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein.

- Wenn Sie **Vollqualifizierten Domänennamen außer Kraft setzen** auswählen, können Sie einen anderen FQDN für die Identität **Interne Webdienste** im Pool angeben. Standardmäßig ist die Einstellung der aktuelle Poolname entsprechend der Definition für den Front-End-Pool.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellungen von Port 80 für http und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, Sie haben bestimmte Anforderungen in Ihrer Organisation und dem Infrastrukturentwurf.

Geben Sie in **Externe Webdienste** Folgendes an:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Anfänglich sind die Standardeinstellungen (Port 8080 für HTTP und Port 4443 für HTTPS) definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf die Standardeinstellungen Port 80 für HTTP und Port 443 für HTTPS festgelegt. Diese Werte bestimmen, welche Ports der Pool auf eingehende Anforderungen überwacht. Normalerweise müssen diese nicht geändert werden, es sei denn, es liegt ein Konflikt zwischen Portanforderungen im Pool vor. Interne und externe veröffentlichte Ports mit denselben Port Werten werden erwartet. Dies stellt keinen Konflikt dar.

### <a name="mediation-server"></a>Vermittlungsserver

Geben Sie in **Vermittlungsserver** Folgendes an:

- Wenn Sie den Vermittlungsserver mit dem Pool verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die Zusammenstellung des Vermittlungsserver aktivieren, definieren Sie den Überwachungs Portbereich auf den Pool Servern für TLS (Transport Layer Security). Standardmäßig ist dieser Port 5067. Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port (Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihrer Gateway-oder PSTN-Anforderungen berufen, um festzustellen, ob dies erforderlich ist. Standardmäßig lautet der Wert des TCP-Ports 5068.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Wenn einem Vermittlungsserver mehr als ein trunk zugeordnet ist, können Sie einen Standard trunk angeben, indem Sie das Gateway auswählen und dann auf **Standard**festlegen klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Front-End-Pool finden Sie unter [Deploying Mediation Servers and Definition Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Standard Edition-Server

Für einen Standard Edition-Server können Sie allgemeine Einstellungen sowie Einstellungen zu Ausfallsicherheit, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**. Beachten Sie, dass dieser Wert nicht geändert werden kann. Sie müssen den Standard Edition-Server entfernen und neu definieren, um den ihm zugeordneten vollqualifizierten Domänennamen ändern zu können.

- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** aus. Wenn Sie den Dienst auf festgelegte IP-Adressen begrenzen möchten, müssen Sie die primäre IP-Adresse festlegen, die der Server für die gesamte Kommunikation außer mit dem Telefonfestnetz verwenden soll. Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt. Sie können auch IPv6 **aktivieren** , um IPv6 für diesen Server zu aktivieren.

- **Aktivieren Sie den Überwachungsport des Hardwaregeräts für den Lastenausgleich**. Aktivieren Sie das Kontrollkästchen, und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status des Servers verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie diesem Server zuweisen möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**. Schließt Audio, Video und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie **Einwahlkonferenzen (PSTN)** auswählen. Ein PSTN-Gateway kann später in den Einstellungen des Vermittlungsservers angegeben und definiert werden.

  - **Enterprise-VoIP**. Aktiviert interne Voice over IP-Anrufe für qualifizierte Mobiltelefone und Geräte und Skype for Business Clients. Zum Aktivieren externer Anruffunktionen müssen Sie einen Vermittlungsserver einschließen. Ausführliche Informationen finden Sie unter "Vermittlungsserver" weiter unten in diesem Thema.

- In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:

  - Wählen Sie **SQL Server Store** aus, um dem Front-End-Server einen SQL Server-Speicher zuzuordnen. Sie können auch die Spiegelung aktivieren und einen Spiegelungs Zeugenserver auswählen.

  - **Dateifreigabe**. Ändern Sie den vom Standard Edition-Server verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**. Ordnen Sie dem Standard Edition-Server einen Archivierungs SQL Server Speicher zu. Sie können aus einem bereits definierten Archivierungsspeicher auswählen, indem Sie den Server aus der Liste auswählen oder auf **neu** klicken, um einen neuen Archivierungsspeicher anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Überwachung (KDS-und QoE-Metriken**. Ordnen Sie dem Standard Edition-Server einen Überwachungs SQL Server Speicher zu. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

  - **Verknüpfen eines Pools mit einem Office-webapps-Server**. Wählen Sie diese Option aus, um dem Front-End-Pool einen Office-webapps-Server zuzuordnen. Wählen Sie einen vorhandenen Server aus der Liste aus, oder klicken Sie auf **neu** , um einen neuen Office-webapps-Server zu erstellen.

  - **Edgepool zuordnen**. Ordnen Sie dem Standard Edition-Server einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

### <a name="resiliency"></a>Flexibilität

Ausfallsicherheit bietet Notfallwiederherstellung und hohe Verfügbarkeit für den Server. Wenn der primäre Server ausfällt, kann durch die Bereitstellung einer Sicherung die Sicherung übernommen werden, sodass sich Benutzer anmelden und kommunizieren können. Es ist möglich, dass die Funktionalität für die Benutzer eingeschränkt ist, je nachdem, welche Systeme ebenfalls fehlgeschlagen sind.

Wählen Sie in der Liste die Front-End-Pool oder Standard Edition-Server aus, die als Sicherung für den Server fungieren sollen. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Durch Aktivieren der Failover-und Fallback-Zeiteinstellungen (in Sekunden angegeben) wird die automatische Erkennung einer fehlgeschlagenen Registrierungsstelle und eine Fallback-Zeit aktiviert, um die automatische Ermittlung der primären Sicherung zu ermöglichen.

> [!IMPORTANT]
> Bei der Definition der Fehlererkennung und des Fallback-Intervalls sollten Sie darauf achten, dass Sie nicht ein Intervall eingeben, das dazu führt, dass Failover und Fallback auftreten, wenn der Server nicht für einen kurzen Zeitraum reagieren kann. Es ist möglich, dass der primäre Server möglicherweise nicht für kurze Zeiträume reagiert, basierend auf dem Laden des Pools oder der Server. Die Standardwerte für Failover und Fallback sind 300 Sekunden und 600 Sekunden für Pool-zu-Pool-oder Pool-Standard Edition-Server. Im Falle einer Survivable Branch Appliance oder eines Survivable Branch Servers in einer Website zu einem Pool oder Standard Edition-Server sind die Standardwerte 120 Sekunden für Failover und 240 Sekunden für Fallback.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Server müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Für **Interne Webdienste** können Sie Folgendes angeben:

- Wenn Sie "Vollqualifizierten Domänennamen außer Kraft setzen" auswählen, können Sie für die Identität "Interne Webdienste" des Servers einen anderen vollqualifizierten Domänennamen angeben. Standardmäßig ist die Einstellung der aktuelle Servername entsprechend der Definition für den Standard Edition-Server.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellung von Port 80 für http und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, Sie haben spezifische Anforderungen in Ihrer Organisation und Ihrem Infrastrukturentwurf.

Für **Externe Webdienste** können Sie Folgendes angeben:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungsports für HTTP und HTTPS. Die Standardeinstellungen von Port 8080 für HTTP und Port 4443 für HTTPS werden zuerst festgelegt. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Diese Werte bestimmen, welche Ports der Server auf eingehende Anforderungen überwacht. Diese Werte müssen zumeist nicht geändert werden, es sei denn, es liegt ein Konflikt bei den Portanforderungen des Servers vor.

### <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:

- Wenn Sie den Vermittlungsserver mit dem Server verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die Zusammenstellungs Vermittlungsserver aktiviert haben, definieren Sie den Überwachungs Portbereich auf dem Server für TLS. Standardmäßig ist dieser Port 5067. Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und Sie sollten sich auf die Anforderungen Ihrer Gateway-oder PSTN-Anforderungen berufen, um festzustellen, ob dies erforderlich ist. Standardmäßig lautet der Wert des TCP-Ports 5068.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Wenn einem Vermittlungsserver mehr als ein Gateway zugeordnet ist, können Sie ein Standardgateway angeben, indem Sie das Gateway auswählen und dann auf **Standard**festlegen klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


