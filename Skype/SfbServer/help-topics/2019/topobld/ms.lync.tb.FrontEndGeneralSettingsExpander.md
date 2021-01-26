---
title: Allgemeine Front-End-Einstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 'Zum Bearbeiten der Einstellungen für einen vorhandenen Front-End-Pool oder Standard Edition-Server werden die folgenden Abschnitte vorgestellt:'
ms.openlocfilehash: d1fa04d2b581fbdb359e01fc776fea8c16d9eb52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833495"
---
# <a name="front-end-general-settings-expander"></a>Allgemeine Front-End-Einstellungen – Erweiterung

Zum Bearbeiten der Einstellungen für einen vorhandenen Front-End-Pool oder Standard Edition-Server werden die folgenden Abschnitte vorgestellt:

- Allgemeine Einstellungen

- Ausfallsicherheitseinstellungen

- Webdiensteinstellungen

- Vermittlungsservereinstellungen

## <a name="front-end-pool"></a>Front-End-Pool

Für einen Front-End-Pool können Sie allgemeine Einstellungen sowie Einstellungen zu Ausfallsicherheit, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für den Front-End-Pool finden Sie unter [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**. Bearbeiten Sie den vollqualifizierten Domänennamen des Pools, um ihn zu ändern.

- **Aktivieren Sie den Port für die Überwachung des Hardwaregeräts zum Lastenausgleich.** Aktivieren Sie das Kontrollkästchen, und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status der Poolserver verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie mit diesem Pool verbinden möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**: Schließt Audio, Video und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie Einwahlkonferenzen (PSTN) auswählen. Im Unterabschnitt zu Vermittlungsservereinstellungen weiter unten in diesem Abschnitt geben Sie ein PSTN-Gateway an und definieren es.

  - **Enterprise-VoIP**. Aktiviert interne Voice-over-IP-Anrufe an qualifizierte Telefone und Geräte sowie Skype for Business-Clients. Zum Aktivieren externer Anruffunktionen müssen Sie einen Vermittlungsserver einschließen. Weitere Informationen finden Sie unter "Vermittlungsserver" weiter später in diesem Thema.

- Bearbeiten Sie in **Zuordnungen** Folgendes, oder geben Sie es an:

  - **SQL-Speicher**. Ändern Einer vorhandenen SQL Server Datenbank oder Erstellen einer neuen SQL Server-basierten Datenbank für die Front-End-Pooldatenbanken. Sie können eine neue Instanz von SQL Server aus der Liste auswählen oder einen neuen Eintrag erstellen, indem Sie auf **"Neu" klicken.**

    Wählen **Sie SQL Server speicherspiegelung** aktivieren, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

    Wählen **Sie SQL Server Spiegelungszeugen** verwenden, um das automatische Failover zu aktivieren, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

  - **Dateifreigabe**. Ändern Sie den vom Front-End-Pool verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**. Ordnen Sie dem Front-End-Pool einen Archivierungsserverspeicher zu. Sie können aus einem bereits definierten Archivierungsspeicher SQL Server auswählen, indem  Sie den Server in der Liste auswählen oder auf "Neu" klicken, um einen neuen Archivierungsserver anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

    Wählen **Sie SQL Server speicherspiegelung** aktivieren, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

    Wählen **Sie SQL Server Spiegelungszeugen** verwenden, um das automatische Failover zu aktivieren, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

  - **Überwachung (CDR- und QoE-Metriken)**. Wählen Sie diese Option aus, SQL Server dem Front-End-Pool einen Überwachungsspeicher zuzuordnen. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

    Wählen **Sie SQL Server speicherspiegelung** aktivieren, und wählen Sie dann den Server aus, der für die Spiegelung verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

    Wählen **Sie SQL Server Spiegelungszeugen** verwenden, um das automatische Failover zu aktivieren, um einen Server auszuwählen, der als Spiegelungszeuge verwendet werden soll. Klicken **Sie auf "Neu",** um einen neuen SQL Server erstellen.

  - **Edgepool zuordnen (für Medienkomponenten)**. Ordnen Sie dem Front-End-Pool einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

  - **Zuordnen eines Pools zu einem Office Web Apps Server**. Wählen Sie diese Option aus, um dem Front-End-Pool einen Office Web Apps Server zuzuordnen. Wählen Sie in der Liste einen vorhandenen Server aus, oder klicken Sie auf **"Neu",** um einen neuen Office Web Apps Server zu erstellen.

### <a name="resiliency"></a>Resilienz

Ausfallsicherheit bietet eine Notfallwiederherstellung und hohe Verfügbarkeit für den Pool. Durch die Bereitstellung einer Sicherung kann der Sicherungsserver die Aufgabe übernehmen, wenn der primäre Server ausfällt, sodass benutzer sich anmelden und kommunizieren können. Je nachdem, welche Systeme mit dem primären Server ausgefallen sind, kann die Funktionalität für Benutzer eingeschränkt sein.

Wählen Sie in der Liste den Front-End-Pool oder Standard Edition-Server aus, der als Sicherungsserver für den Pool fungieren soll. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Das Aktivieren der (in Sekunden angegebenen) Failover- und Fallbackzeiteinstellungen ermöglicht die automatische Erkennung eines ausgefallenen Servers und eine Ausweichzeit, um automatisch zu bestimmen, ob der primäre Server wieder verfügbar ist.

> [!IMPORTANT]
> Beim Definieren der Fehlererkennung und des Fallbackintervalls sollten Sie darauf achten, kein Intervall ein betreten, das das Failover und das Fallback verursacht, wenn der Server für einen kurzen Zeitraum nicht reagiert. Es ist möglich, dass der primäre Server je nach Laden des Pools oder der Server möglicherweise für kurze Zeit nicht reagiert. Die Standardwerte für Failover und Fallback sind 300 Sekunden und 600 Sekunden für Pool zu Pool oder Pool zu Standard Edition-Server. Bei einer Survivable Branch Appliance oder einem Survivable Branch Server an einem Standort für einen Pool oder Standard Edition-Server sind die Standardwerte 120 Sekunden für failover und 240 Sekunden für fallback.

> [!CAUTION]
> Der Mindestwert für das **Failoverintervall** sollte nicht unter 90 Sekunden festgelegt werden. Wenn Sie den Wert auf weniger als 90 Sekunden festlegen, wird der Wert von 90 Sekunden verwendet. Die Pingzeit zwischen Clustern beträgt 30 Sekunden, und eine Einstellung unter 90 Sekunden kann dazu führen, dass der primäre Server und der Sicherungsserver nach oben und unten fahren, was zu unerwünschten Auswirkungen auf die Produktion führt, da die Server versuchen, den brauchbaren Status des anderen Servers zu beheben. Weniger als 90 Sekunden lassen nicht genügend Zeit zu, um festzustellen, ob der primäre Server tatsächlich nicht verfügbar ist oder nicht.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Front-End-Pool müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Geben Sie in **Interne Webdienste** Folgendes an:

> [!CAUTION]
> Wenn Sie über mehrere Front-End-Pools oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Servers als **pool01.contoso.com** definieren, können Sie pool01.contoso.com nicht für einen anderen Front-End-Pool oder **Front-End-Server** verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN der externen Webdienste, der für einen Director oder Directorpool definiert ist, von jedem anderen Director oder Directorpool sowie von jedem Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN überschreiben möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder Directorpool eindeutig sein.

- Wenn Sie **Vollqualifizierten Domänennamen außer Kraft setzen** auswählen, können Sie einen anderen FQDN für die Identität **Interne Webdienste** im Pool angeben. Standardmäßig ist die Einstellung der aktuelle Poolname entsprechend der Definition für den Front-End-Pool.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellungen von Port 80 für HTTP und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, Sie haben bestimmte Anforderungen in Ihrem Organisations- und Infrastrukturentwurf.

Geben Sie in **Externe Webdienste** Folgendes an:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Anfänglich sind die Standardeinstellungen (Port 8080 für HTTP und Port 4443 für HTTPS) definiert. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Die veröffentlichten Ports sind auf die Standardeinstellungen Port 80 für HTTP und Port 443 für HTTPS festgelegt. Diese Werte bestimmen, welche Ports der Pool auf eingehende Anforderungen überwacht. In der Regel müssen diese nicht geändert werden, es sei denn, es liegt ein Konflikt mit den Portanforderungen für den Pool vor. Interne und externe veröffentlichte Ports mit denselben Portwerten werden erwartet. Dies stellt keinen Konflikt dar.

### <a name="mediation-server"></a>Vermittlungsserver

Geben Sie in **Vermittlungsserver** Folgendes an:

- Wenn Sie den Vermittlungsserver mit dem Pool verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die Kollokation des Vermittlungsservers aktivieren, definieren Sie den Überwachungsportbereich auf den Poolservern für TLS (Transport Layer Security). Standardmäßig ist dieser Port 5067. Wenn Sie **"TCP-Port aktivieren"** auswählen, müssen Sie einen Tcp-Port (Transmission Control Protocol) für den angeschlossenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und Sie sollten sich an die Anforderungen Ihres Gateways oder Ihres PstNs wenden, um festzustellen, ob Sie dies benötigen. Standardmäßig ist der Wert des TCP-Ports 5068.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Wenn einem Vermittlungsserver mehrere Trunks zugeordnet sind, können Sie einen Standard trunk angeben, indem Sie das Gateway auswählen und dann auf **"Standard" klicken.** Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für den Front-End-Pool finden Sie unter [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

## <a name="standard-edition-server"></a>Standard Edition-Server

Für einen Standard Edition-Server können Sie allgemeine Einstellungen sowie Einstellungen zu Ausfallsicherheit, Webdiensten und Vermittlungsservern konfigurieren. Ausführliche Informationen finden Sie in den folgenden Unterabschnitten. Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).

### <a name="general-settings"></a>Allgemeine Einstellungen

Die folgenden allgemeinen Einstellungen können konfiguriert werden:

- **FQDN**. Beachten Sie, dass dieser Wert nicht geändert werden kann. Sie müssen den Standard Edition-Server entfernen und neu definieren, um den ihm zugeordneten vollqualifizierten Domänennamen ändern zu können.

- Wählen Sie **Alle konfigurierten IP-Adressen verwenden** oder **Dienstnutzung auf ausgewählte IP-Adressen beschränken** aus. Wenn Sie den Dienst auf festgelegte IP-Adressen begrenzen möchten, müssen Sie die primäre IP-Adresse festlegen, die der Server für die gesamte Kommunikation außer mit dem Telefonfestnetz verwenden soll. Für die Verwendung mit dem Telefonfestnetz wird eine gesonderte IP-Adresse bestimmt. Sie können auch **"IPv6 aktivieren" auswählen,** um IPv6 für diesen Server zu aktivieren.

- **Aktivieren Sie den Überwachungsport des Hardwaregeräts für den Lastenausgleich**. Aktivieren Sie das Kontrollkästchen, und geben Sie die Portnummer ein, die Ihr Hardwaregerät für den Lastenausgleich zum Überwachen des Status des Servers verwendet.

- Definieren Sie in **Funktionen und Funktionalität** die zusätzlichen Rollen, die Sie diesem Server zuweisen möchten. Sie können die folgenden Einstellungen konfigurieren:

  - **Konferenz**. Schließt Audio, Video und Anwendungsfreigabe ein. Nach Auswahl dieser Option können Sie **Einwahlkonferenzen (PSTN)** auswählen. Ein PSTN-Gateway kann später in den Einstellungen des Vermittlungsservers angegeben und definiert werden.

  - **Enterprise-VoIP**. Aktiviert interne Voice-over-IP-Anrufe an qualifizierte Telefone und Geräte sowie Skype for Business-Clients. Zum Aktivieren externer Anruffunktionen müssen Sie einen Vermittlungsserver einschließen. Weitere Informationen finden Sie unter "Vermittlungsserver" weiter später in diesem Thema.

- In **Zuordnungen** können Sie Folgendes bearbeiten oder angeben:

  - Wählen **SQL Server speicher,** um einen SQL Server dem Front-End-Server zuzuordnen. Sie können auch die Spiegelung aktivieren und einen Spiegelungszeugenserver auswählen.

  - **Dateifreigabe**. Ändern Sie den vom Standard Edition-Server verwendeten Dateispeicher. In der Liste können Sie aus den bereits definierten Dateispeichern einen neuen auswählen. Oder Sie können einen neuen Dateispeicher erstellen, indem Sie auf **Neu** klicken.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Archivierung**. Ordnen Sie dem Standard SQL Server einen Archivierungsspeicher zu. Sie können einen bereits definierten Archivierungsspeicher auswählen, indem  Sie in der Liste den Server auswählen oder auf "Neu" klicken, um einen neuen Archivierungsspeicher anzugeben.

    > [!IMPORTANT]
    > Vor Veröffentlichung der neu definierten Topologie muss der angegebene Server bereits vorhanden und der Domäne beigetreten sein.

  - **Überwachung (CDR- und QoE-Metriken).** Ordnen Sie dem Standard SQL Server einen Überwachungsspeicher zu. Sie können in der Liste einen bereits definierten Monitoring Server auswählen oder auf **Neu** klicken, um einen neuen Monitoring Server anzugeben.

  - **Zuordnen eines Pools zu einem Office Web Apps Server**. Wählen Sie diese Option aus, um dem Front-End-Pool einen Office Web Apps Server zuzuordnen. Wählen Sie in der Liste einen vorhandenen Server aus, oder klicken Sie auf **"Neu",** um einen neuen Office Web Apps Server zu erstellen.

  - **Edgepool zuordnen**. Ordnen Sie dem Standard Edition-Server einen Edgeserver oder -pool zu. Sie können in der Liste einen bereits definierten Edgeserver oder -pool auswählen oder auf **Neu** klicken, um einen neuen Edgeserver oder -pool anzugeben.

### <a name="resiliency"></a>Resilienz

Ausfallsicherheit bietet eine Notfallwiederherstellung und hohe Verfügbarkeit für den Server. Durch die Bereitstellung einer Sicherung kann die Sicherung übernehmen, wenn der primäre Server ausfällt, sodass benutzer sich anmelden und kommunizieren können. Je nachdem, welche Systeme ebenfalls ausgefallen sind, kann es zu einer eingeschränkten Funktionalität für Benutzer kommen.

Wählen Sie in der Liste den Front-End-Pool oder Standard Edition-Server aus, der als Sicherung für den Server dient. Sie können außerdem Zeitintervalle für Failover und Fallback auswählen. Das Aktivieren der (in Sekunden angegebenen) Failover- und Fallbackzeiteinstellungen ermöglicht die automatische Erkennung einer ausgefallenen Registrierung und eine Ausweichzeit, um automatisch zu bestimmen, ob die primäre Registrierung wieder verfügbar ist.

> [!IMPORTANT]
> Beim Definieren der Fehlererkennung und des Fallbackintervalls sollten Sie darauf achten, kein Intervall ein betreten, das das Failover und das Fallback verursacht, wenn der Server für einen kurzen Zeitraum nicht reagieren sollte. Es ist möglich, dass der primäre Server aufgrund des Ladens des Pools oder der Server möglicherweise für kurze Zeit nicht reagiert. Die Standardwerte für Failover und Fallback sind 300 Sekunden und 600 Sekunden für Pool zu Pool oder Pool zu Standard Edition-Server. Bei einer Survivable Branch Appliance oder einem Survivable Branch Server an einem Standort für einen Pool oder Standard Edition-Server sind die Standardwerte 120 Sekunden für failover und 240 Sekunden für fallback.

### <a name="web-services"></a>Webdienste

Zum Bearbeiten oder Angeben weiterer Einstellungen für Webdienste für den Server müssen Sie in **Interne Webdienste** und **Externe Webdienste** Einstellungen ändern bzw. angeben.

Für **Interne Webdienste** können Sie Folgendes angeben:

- Wenn Sie "Vollqualifizierten Domänennamen außer Kraft setzen" auswählen, können Sie für die Identität "Interne Webdienste" des Servers einen anderen vollqualifizierten Domänennamen angeben. Standardmäßig ist die Einstellung der aktuelle Servername entsprechend der Definition für den Standard Edition-Server.

- Für die Bereitstellung erforderliche Überwachungs- und veröffentlichte Ports für HTTP und HTTPS. Die Standardeinstellung von Port 80 für HTTP und Port 443 für HTTPS sind die am häufigsten verwendeten Einstellungen und müssen in der Regel nicht geändert werden, es sei denn, Sie haben bestimmte Anforderungen in Ihrem Organisations- und Infrastrukturentwurf.

Für **Externe Webdienste** können Sie Folgendes angeben:

- Den vollqualifizierten Domänennamen der externen Webdienste. Der hier angegebene FQDN wird meist von den externen Verbindungsanforderungen bestimmt, z. B. dem Reverseproxy.

- Für die Bereitstellung erforderliche Überwachungsports für HTTP und HTTPS. Die Standardeinstellungen von Port 8080 für HTTP und Port 4443 für HTTPS werden zuerst festgelegt. Sie können diese Einstellungen für die Überwachungsports basierend auf den Anforderungen für den Reverseproxy und das externe Netzwerk ändern. Diese Werte bestimmen, welche Ports der Server auf eingehende Anforderungen überwacht. Diese Werte müssen zumeist nicht geändert werden, es sei denn, es liegt ein Konflikt bei den Portanforderungen des Servers vor.

### <a name="mediation-server"></a>Vermittlungsserver

Für **Vermittlungsserver** können Sie Folgendes angeben:

- Wenn Sie den Vermittlungsserver mit dem Server verbinden, müssen Sie das Kontrollkästchen **Verbundener Vermittlungsserver aktiviert** aktivieren. Wenn Sie den Vermittlungsserver nicht verbinden möchten, ist keine der Einstellungen in diesem Abschnitt verfügbar.

- Wenn Sie die Kollokation des Vermittlungsservers aktiviert haben, definieren Sie den Bereich des Abhörports auf dem Server für TLS. Standardmäßig ist dieser Port 5067. Wenn Sie **"TCP-Port aktivieren"** auswählen, müssen Sie einen "TCP"-Port für den angeschlossenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und Sie sollten sich an die Anforderungen Ihres Gateways oder Ihres PstNs wenden, um festzustellen, ob Sie dies benötigen. Standardmäßig ist der Wert des TCP-Ports 5068.

- Trunks, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Trunks definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

- Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, können Sie ein Standardgateway angeben, indem Sie das Gateway auswählen und dann auf **"Standard" klicken.** Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


