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
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 'Zum Bearbeiten der Einstellungen eines vorhandenen Front-End-Pools oder Standard Edition-Servers stehen die folgenden Abschnitte zur Verfügung:'
ms.openlocfilehash: 8533d8be1e128b34d1fd8bf9280c1704a585fd46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684678"
---
# <a name="front-end-general-settings-expander"></a>Allgemeine Front-End-Einstellungen – Erweiterung

Zum Bearbeiten der Einstellungen eines vorhandenen Front-End-Pools oder Standard Edition-Servers stehen die folgenden Abschnitte zur Verfügung:

- Allgemeine Einstellungen

- Flexibilitätseinstellungen

- Webdiensteinstellungen

- Vermittlungsservereinstellungen

## <a name="front-end-pool"></a>Front-End-Pool

Für einen Front-End-Pool können Sie allgemeine Einstellungen sowie Einstellungen zu Flexibilität, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Front-End-Pool finden Sie unter [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**: Bearbeiten Sie den vollqualifizierten Domänennamen des Pools, um ihn zu ändern.

- **Überwachungsport für Hardwaregerät zum Lastenausgleich aktivieren**: Aktivieren Sie das Kontrollkästchen und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status der Poolserver verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie mit diesem Pool verbinden möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**: Schließt Audio-, Video- und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie Einwahlkonferenzen (PSTN) auswählen. Im Unterabschnitt zu „Vermittlungsservereinstellungen“ weiter unten in diesem Abschnitt können Sie ein PSTN-Gateway angeben und definieren.

  - **Enterprise-VoIP** Ermöglicht interne VoIP-Anrufe an qualifizierte Handapparate und Geräte sowie an Skype for Business-Clients. Um externe Anruffunktionen zu aktivieren, müssen Sie einen Vermittlungs Server einbeziehen. Ausführliche Informationen finden Sie weiter unten in diesem Thema unter "Vermittlungs Server".

- Bearbeiten Sie in **Zuordnungen** Folgendes bzw. geben Sie Folgendes an:

  - **SQL-Speicher**: Ändern Sie eine vorhandene SQL Server-Datenbank oder erstellen Sie eine neue SQL Server-Datenbank zum Speichern der Front-End-Pooldatenbanken. Sie können in der Liste eine neue SQL Server-Instanz auswählen oder durch Klicken auf **Neu** einen neuen Eintrag erstellen.

    Wählen Sie die Option **SQL Server-Speicherspiegelung aktivieren** und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

    Wählen Sie die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

  - **Dateifreigabe**. Ändern Sie den vom Front-End-Pool verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**: Ordnen Sie dem Front-End-Pool einen Archivierungsserverspeicher zu. Sie können in der Liste einen bereits definierten SQL Server-Speicher für die Archivierung auswählen oder auf **Neu** klicken, um einen neuen Archivierungsserver anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

    Wählen Sie die Option **SQL Server-Speicherspiegelung aktivieren** und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

    Wählen Sie die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

  - **Überwachung (CDR- und QoE-Metriken)**: Wählen Sie diese Option aus, um dem Front-End-Pool einen SQL Server-Speicher für die Überwachung zuzuordnen. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

    Wählen Sie die Option **SQL Server-Speicherspiegelung aktivieren** und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

    Wählen Sie die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken Sie auf **Neu**, um einen neuen SQL Server-Speicher zu erstellen.

  - **Edgepool zuordnen (für Medienkomponenten)**: Ordnen Sie dem Front-End-Pool einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

  - **Pool einem Office Web Apps-Server zuordnen**: Wählen Sie diese Option aus, um dem Front-End-Pool einen Office Web Apps Server zuzuordnen. Sie können in der Liste einen vorhandenen Server auswählen oder auf **Neu** klicken, um einen neuen Office Web Apps-Server zu erstellen.

### <a name="resiliency"></a>Flexibilität

Dank der Flexibilität (Ausfallsicherheit) ist die Notfallwiederherstellung und hohe Verfügbarkeit des Pools gewährleistet. Durch Bereitstellung einer Sicherung für den Fall eines Ausfalls des primären Servers kann der Sicherungsserver übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme mit dem primären Server ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.

Wählen Sie in der Liste den Front-End-Pool oder den Standard Edition-Server aus, der als Sicherungsserver für den Pool fungiert. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung eines ausgefallenen Servers sowie einen Zeitpuffer zur automatischen Bestimmung, ob die primäre Komponente wieder betriebsbereit ist.

> [!IMPORTANT]
> Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn der Server kurzfristig nicht reagieren sollte. Je nach Auslastung des Pools oder der Server ist es möglich, dass der primäre Server ggf. kurzfristig nicht reagiert. Die Standardwerte für Failover und Fallback sind 300 bzw. 600 Sekunden zwischen Pools bzw. Pool und Standard Edition-Server. Zwischen einer Survivable Branch-Anwendung oder einem Survivable Branch Server an einem Standort und einem Pool bzw. Standard Edition-Server sind die Standardwerte 120 Sekunden für Failover und 240 Sekunden für Fallback.

> [!CAUTION]
> Der Mindestwert für das **Failoverintervall** sollte auf mindestens 90 Sekunden festgelegt werden. Wenn Sie den Wert auf weniger als 90 Sekunden festlegen, wird ein Wert von 90 Sekunden verwendet. Die Pingzeit zwischen Clustern beträgt 30 Sekunden. Eine Einstellung von weniger als 90 Sekunden kann zu einem ständigen Wechsel zwischen primärem Server und Sicherungsservern führen. Dies hat unerwünschte Auswirkungen auf die Produktion, da beide Server versuchen, den Status des jeweils anderen aufzulösen. In weniger als 90 Sekunden kann nicht bestimmt werden, ob der primäre Server tatsächlich nicht verfügbar ist.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Front-End-Pool müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Geben Sie in **Interne Webdienste** Folgendes an:

> [!CAUTION]
> Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als **pool01.contoso.com**definieren, können Sie **pool01.contoso.com** nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie sich entscheiden, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

- Wenn Sie **Vollqualifizierten Domänennamen außer Kraft setzen** auswählen, können Sie einen anderen FQDN für die Identität **Interne Webdienste** im Pool angeben. Standardmäßig ist die Einstellung der aktuelle Poolname entsprechend der Definition für den Front-End-Pool.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellungen von Port 80 für HTTP und Port 443 für HTTPS sind die gängigsten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, in Ihrem Organisations- und Infrastrukturentwurf liegen besondere Anforderungen vor.

Geben Sie unter **Externe Webdienste** Folgendes an:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungsports und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellungen von Port 8080 für http und Port 4443 für HTTPS werden zunächst definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf Standard Port 80 für http und Port 443 für HTTPS eingestellt. Diese Werte legen fest, welche Ports vom Pool auf eingehende Anforderungen überwacht werden. In der Regel müssen diese nicht geändert werden, es sei denn, es liegt ein Konflikt zwischen den Portanforderungen im Pool vor. Interne und externe veröffentlichte Ports, die dieselben Portwerte verwenden, werden erwartet. Dies ist kein Konflikt.

### <a name="mediation-server"></a>Vermittlungsserver

Geben Sie in **Vermittlungsserver** Folgendes an:

- Wenn Sie den Vermittlungsserver mit dem Pool verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die Kollokation des Vermittlungsservers aktivieren, müssen Sie den Überwachungsportbereich der Poolserver für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Falls einem Vermittlungsserver mehr als ein Trunk zugeordnet ist, können Sie einen Trunk als Standard angeben, indem Sie das Gateway auswählen und auf **Als Standardeinstellung festlegen** klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Front-End-Pool finden Sie unter [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Standard Edition-Server

Für einen Standard Edition-Server können Sie allgemeine Einstellungen sowie Einstellungen zu Ausfallsicherheit, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**. Beachten Sie, dass der FQDN nicht geändert werden kann. Sie müssen den Standard Edition-Server entfernen und neu definieren, um den ihm zugeordneten FQDN zu ändern.

- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf die ausgewählten IP-Adressen beschränken**. Wenn Sie den Dienst auf festgelegte IP-Adressen begrenzen möchten, müssen Sie die primäre IP-Adresse festlegen, die der Server für die gesamte Kommunikation mit Ausnahme des Telefonfestnetzes verwenden soll. Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt. Sie können auch **IPv6 aktivieren** wählen, um IPv6 für diesen Server zu aktivieren.

- **Aktivieren Sie den Überwachungsport des Hardwaregeräts für den Lastenausgleich**. Aktivieren Sie das Kontrollkästchen, und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status des Servers verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie diesem Server zuweisen möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**. Schließt Audio-, Video- und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie **Einwahlkonferenzen (PSTN)** auswählen. Ein PSTN-Gateway kann später in den Einstellungen des Vermittlungsservers angegeben und definiert werden.

  - **Enterprise-VoIP** Ermöglicht interne VoIP-Anrufe an qualifizierte Handapparate und Geräte sowie an Skype for Business-Clients. Um externe Anruffunktionen zu aktivieren, müssen Sie einen Vermittlungs Server einbeziehen. Ausführliche Informationen finden Sie weiter unten in diesem Thema unter "Vermittlungs Server".

- In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:

  - Wählen Sie **SQL Server-Speicher**, um dem Front-End-Server einen SQL Server-Speicher zuzuordnen. Außerdem können Sie die Spiegelung aktivieren und einen Spiegelungszeugenserver auswählen.

  - **Dateifreigabe**. Ändern Sie den vom Standard Edition-Server verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**: Ordnen Sie dem Standard Edition-Server einen SQL Server-Speicher für die Archivierung zu. Sie können in der Liste einen bereits definierten Archivierungsspeicher auswählen oder auf **Neu** klicken, um einen neuen Archivierungsspeicher anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Überwachung (CDR- und QoE-Metriken)**: Ordnen Sie dem Standard Edition-Server einen SQL Server-Speicher für die Überwachung zu. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

  - **Pool einem Office Web Apps-Server zuordnen**: Wählen Sie diese Option aus, um dem Front-End-Pool einen Office Web Apps Server zuzuordnen. Sie können in der Liste einen vorhandenen Server auswählen oder auf **Neu** klicken, um einen neuen Office Web Apps-Server zu erstellen.

  - **Edgepool zuordnen**. Ordnen Sie dem Standard Edition-Server einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

### <a name="resiliency"></a>Flexibilität

Dank der Flexibilität (Ausfallsicherheit) ist die Notfallwiederherstellung und hohe Verfügbarkeit des Servers gewährleistet. Durch Bereitstellung einer Sicherung für den Fall eines Ausfalls des primären Servers kann die Sicherungskomponente übernehmen und Benutzern die Anmeldung und Kommunikation ermöglichen. Bei Benutzern kann es, je nachdem, welche Systeme zusätzlich ausgefallen sind, möglicherweise zu einer eingeschränkten Funktionalität kommen.

Wählen Sie in der Liste den Front-End-Pool oder den Standard Edition-Server aus, der als Sicherungskomponente für den Server fungiert. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Die (in Sekunden angegebenen) Zeiteinstellungen für Failover und Fallback ermöglichen die automatische Erkennung einer ausgefallenen Registrierungsstelle sowie einen Zeitpuffer zur automatischen Bestimmung, ob die primäre Komponente wieder betriebsbereit ist.

> [!IMPORTANT]
> Wenn Sie das Ausfall- und Fallbackerkennungsintervall festlegen, sollten Sie kein Intervall eingeben, das für das Auslösen eines Failovers oder Fallbacks sorgt, wenn der Server kurzfristig nicht reagieren sollte. Je nach Auslastung des Pools oder der Server ist es möglich, dass der primäre Server ggf. kurzfristig nicht reagiert. Die Standardwerte für Failover und Fallback sind 300 bzw. 600 Sekunden zwischen Pools bzw. zwischen Pool und Standard Edition-Server. Zwischen einer Survivable Branch-Anwendung oder einem Survivable Branch Server an einem Standort und einem Pool bzw. Standard Edition-Server sind die Standardwerte 120 Sekunden für Failover und 240 Sekunden für Fallback.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Server müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Für **Interne Webdienste** können Sie Folgendes angeben:

- Wenn Sie "Vollqualifizierten Domänennamen außer Kraft setzen" auswählen, können Sie für die Identität "Interne Webdienste" des Servers einen anderen vollqualifizierten Domänennamen angeben. Standardmäßig ist die Einstellung der aktuelle Servername entsprechend der Definition für den Standard Edition-Server.

- Für die Bereitstellung erforderliche Überwachungsports und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellungen von Port 80 für HTTP und Port 443 für HTTPS sind die gängigsten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, in Ihrem Organisations- und Infrastrukturentwurf liegen besondere Anforderungen vor.

Für **Externe Webdienste** können Sie Folgendes angeben:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungsports für HTTP und HTTPS. Die Standardeinstellungen von Port 8080 für HTTP und Port 4443 für HTTPS werden zuerst festgelegt. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Diese Werte bestimmen, welche Ports der Server auf eingehende Anforderungen überwacht. Diese Werte müssen zumeist nicht geändert werden, es sei denn, es liegt ein Konflikt bei den Portanforderungen des Servers vor.

### <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:

- Wenn Sie den Vermittlungsserver mit dem Server verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für TLS festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Falls einem Vermittlungsserver mehr als ein Gateway zugeordnet ist, können Sie ein Gateway als Standard angeben, indem Sie das Gateway auswählen und auf **Als Standardeinstellung festlegen** klicken. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


