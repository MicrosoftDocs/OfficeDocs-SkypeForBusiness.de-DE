---
title: Plan für die Archivierung in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie für die Archivierung in Skype für Business Server planen.'
ms.openlocfilehash: 164a3207153986e788a7db47b86014063e37e0e5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236116"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Plan für die Archivierung in Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie für die Archivierung in Skype für Business Server planen.
  
Unternehmen und andere Organisationen müssen eine zunehmende Anzahl von Rechtsvorschriften beachten, die die Speicherung bestimmter Kommunikationsarten erfordern. Wenn Ihre Organisation solche Anforderungen verfügt, können Sie Archivierung in Skype für Business Server zum Archivieren von Sofortnachrichten (IM) und Communications Konferenzen (Besprechungen), mit denen die Compliance-Bestimmungen zu unterstützen.
  
## <a name="archiving-components"></a>Archivierungskomponenten

Skype für Business Server verwendet die folgenden Archivierung Komponenten:
  
- **Archivierungs-Agents**. Archivierungs-Agents (die auch als einheitliche Datenerfassungs-Agents bezeichnet werden) werden automatisch in jedem Enterprise Edition-Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert. Auch wenn die Archivierungs-Agents automatisch aktiviert werden, werden Nachrichten erst dann erfasst, wenn die Archivierung aktiviert und entsprechend konfiguriert wurde. Standardmäßig ist die Archivierung deaktiviert.
    
- **Archivierungsdatenspeicher**. Datenspeicher für Skype für Business Server kann, wenn Sie eine Exchange-Bereitstellung haben mit Exchange-Speicher als Skype für Business Server SQL Server-Datenbanken implementiert, oder integriert werden. 
    
Die Archivierung erfordert auch Dateispeicher. Es wird jedoch der gleiche Dateispeicher wie für Front-End- und Standard Edition-Server verwendet.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Bestimmen der Archivierungsanforderungen Ihrer Organisation

Um die Archivierung zu implementieren, müssen Sie entscheiden, wie Sie erfüllen die Anforderungen Ihrer Organisation für die Archivierung, indem Sie Folgendes festlegen:
  
- **Wahl der richtigen Speicheroption**. Es gibt zwei Möglichkeiten, Speicher zu implementieren (Sie können auch eine Kombination aus beiden verwenden):
    
  - **Exchange-Speicher.** Wenn Sie eine Exchange-Bereitstellung verfügen, können Sie Skype für Business Server und Exchange-Archivierung integrieren, damit Ihre Skype für Business Server und Daten in Exchange archiviert werden zusammen in Exchange gespeichert. Wenn Sie die Option Microsoft Exchange-Integration aktivieren, verwaltet von Benutzerpostfächern bei der Verwendung von Exchange Server Exchange-Speicher für archivierte Daten, aber haben nur wenn sich die Postfächer Compliance-Archiv versetzt wurde. Microsoft Exchange-Integration ist standardmäßig nicht aktiviert.
    
  - **Skype für Business Server-Speicher.** Wenn Sie Benutzer, die nicht auf Exchange verwaltet werden oder hatten, die nicht ihren Postfächern Compliance-Archiv zu platzieren, oder wenn Sie nicht Microsoft Exchange-Integration für einige oder alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie Skype für Business Server-Archivierungsdatenbanken mit bereitstellen S SQL Server.
    
- **Zeitpunkt der Archivierungsbereitstellung.** Sie können im Rahmen Ihrer ursprünglichen Skype für Business Server-Bereitstellung Archivierung bereitstellen, oder Sie können mit einer vorhandenen Bereitstellung hinzufügen. Verwendung von Skype für Business Server-Archivierungsspeicher (SQL Server-Datenbanken) verwenden, Topologie-Generator, um Ihre Topologie die Datenbanken hinzuzufügen, und veröffentlichen die Topologie dann erneut. Wenn alle Benutzer sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren, Sie müssen keine Aktualisieren Ihrer Topologie, jedoch müssen nur zum Speichern von archivierter Daten im Exchange Microsoft Exchange-Integration aktivieren. 
    
- **Standorte und Benutzer in der Organisation, die eine Archivierung benötigen**. Sie können die archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Standorte, Pools, Benutzer und Benutzergruppen konfigurieren.
    
- **Archivierungsinhalte**. Soll die Archivierung auf globaler Ebene oder für bestimmte Standorte und Benutzer durchgeführt werden, müssen sie für jede dieser Ebenen festlegen, ob die folgenden Arten von Inhalten aktiviert werden sollen oder nicht: 
    
  - Peer-zu-Peer-Chatnachrichten
    
  - Konferenzen (Besprechungen), die Teil von Chatsitzungen mit mehreren Teilnehmern sind
    
  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)
    
  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz
    
- **Nicht archivierbare Inhalte**. Die folgenden Arten von Inhalten können nicht archiviert werden: 
    
  - Peer-to-Peer-Dateiübertragungen
    
  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen
    
  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -konferenzen
    
    Skype für Business Server archivieren beständigen Chat Unterhaltungen auch nicht. Unterhaltungen beständigen Chat archivieren möchten, müssen Sie aktivieren und konfigurieren die Einhaltung von Bestimmungen, also eine Komponente, die mit Persistent Chat Server bereitgestellt werden können. Weitere Informationen hierzu finden Sie unter [Planen von Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 
    
- **Dauer der Aufbewahrung archivierter Daten**. Die Archivierungsdatenbank kann nicht für die langfristige Aufbewahrung und Skype für Business Server bietet keiner (Suche) e-Discovery-Lösung für archivierte Daten, damit Daten in einen anderen Speicher verschoben werden müssen. Skype für Business Server bietet eine Sitzung Export-Tool können Sie die archivierte Daten exportieren, und die durchsuchbaren Protokolle von archivierten Daten erstellt. 
    
     Für die globale Richtlinie, und für jede Website und Benutzerrichtlinien, die Sie erstellen, können Sie wann archivierte und exportierte Daten zu löschen angeben. Weitere Informationen zum Löschen der Daten finden Sie unter [Verwalten der Löschung von archivierten Daten in Skype für Business Server](../../manage/archiving/purging-of-archived-data.md). Weitere Informationen zur Verwendung der Sitzung exportieren Sie Tool, finden Sie unter [Exportieren von archivierten Daten in Skype für Business Server](../../manage/archiving/export-archived-data.md).
    
- **Archivierung der internen oder externen Kommunikation**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (Kommunikationen, an denen mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    > [!NOTE]
    > Steuern der Archivierung für interne oder externe Kommunikation ist nur verfügbar für Skype für Business-Richtlinie. Für die Exchange-integrierte Archivierung sind interne und externe Kommunikation archiviert oder nicht archiviert. 
  
- **Implementierung des kritischen Modus**. Wenn die Archivierung für Ihre Organisation erforderlich ist, blockiert Konfigurieren von kritischen Modus im- und konferenzsitzungen im Falle einer Skype für Business Serverausfall, die Archivierung verhindern würden. Beispiel: 
    
  - Ein Problem mit der Skype für Business Server Speicherdienst. In diesem Fall werden Chatnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
  - Eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst. In diesem Fall werden aktive Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Auswählen der Archivierungsbereitstellung und Konfigurationsoptionen

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert. Die Konfiguration der Archivierung ist dabei abhängig von Ihrer Bereitstellung. Es gibt mehrere Möglichkeiten, die Archivierung bereitzustellen:
  
- Verwenden Sie Microsoft Exchange-Speicher
    
- Verwenden Sie Skype für Business Server-Speichers
    
> [!NOTE]
> Wenn Sie beide Skype für Business Server-Archivierungsdatenbanken implementieren und Microsoft Exchange-Integration aktivieren, Exchange-Richtlinien außer Kraft setzen Skype für Business Server Archivierungsrichtlinien, jedoch nur für Benutzer, die in Exchange verwaltet werden und hatten ihren Postfächern versetzt auf Compliance-Archiv. Skype für die Archivierung Business hängt von der Microsoft Exchange-Compliance-Archiv-Richtlinie. 
  
Wenn Sie die Archivierung für einen Front-End-Pool oder Standard Edition-Server bereitstellen, sollten Sie es für alle anderen Front-End-Pools und Standard Edition-Servern in Ihrer Bereitstellung aktivieren. Wenn die Archivierung nicht auf dem Pool aktiviert wird, auf dem eine Unterhaltung oder Besprechung verwaltet wird, können keine Konferenzdaten archiviert werden. Die Archivierung funktioniert zwar noch für Chatnachrichten, aber Konferenzinhalte und -ereignisse können nicht archiviert werden.
  
> [!NOTE]
> Zum Aktivieren der Delegierung administrativer Aufgaben Beibehaltung Ihrer Organisation Sicherheitsstandards verwendet Skype für Business Server rollenbasierte Zugriffssteuerung (RBAC). Bei der rollenbasierten Zugriffssteuerung werden Administratorrechte zugewiesen, indem Benutzer vordefinierten Administrationsrollen hinzugefügt werden. Zum Konfigurieren der Skype Business Archivierungsrichtlinien und-Konfigurationen muss der Benutzer auf die Rolle "csarchivingadministrator" zugewiesen werden (es sei denn, die Konfiguration direkt auf dem Server abgeschlossen ist, auf dem Archivierung, anstatt Remote bereitgestellt wird, von einem anderen Computer ). Eine Liste mit den Benutzerrechten Berechtigungen und Rollen erforderlich für die Bereitstellung, Archivierung finden Sie unter [Deploy Archivierung für Skype für Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration verwenden, erfordert eine Konfiguration von Exchange-Richtlinien über entsprechende Administratorrechte und-Berechtigungen. Weitere Informationen hierzu finden Sie unter der Exchange-Dokumentation. 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher

 Wenn Sie Microsoft Exchange-Integration auswählen, verwenden Sie Exchange-Richtlinien und Konfigurationen zur Steuerung der Archivierung von Skype für Business Server. Sie können die Option Microsoft Exchange-Integration auf globaler Ebene, Standortebene und Poolebene konfigurieren. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen Skype für Business Server und Exchange synchronisieren. Außerdem müssen Sie folgendes festlegen:
  
- Zu archivierende Elemente (Chatnachrichten, Konferenzen oder beides)
    
- Ob kritischen Modus implementiert die im- und konferenzsitzungen im Fall eines WAN-einen Skype für Business Serverausfall blockiert 
    
- Auswahl der Option Microsoft Exchange-Integration mit Exchange zum Speichern von archivierten Daten
    
Informationen zum Konfigurieren von Exchange In-Place Hold Richtlinien und Einstellungen, die Unterstützung der Archivierung finden Sie unter der Exchange-Produktdokumentation.
  
### <a name="skype-for-business-server-storage"></a>Speicher in Skype for Business Server

Wenn Sie für den Serverspeicher Business Skype auswählen, verwenden Sie Skype für Business Server Archivierungsrichtlinien und-Konfigurationen und steuern, Archivierung aktiviert implementiert wird. Skype für den Serverspeicher Business verwendet SQL Server-Datenbanken, sodass Sie die entsprechenden SQL Server-Datenbanken Ihrer Topologie hinzufügen und dann Ihr Archivierungsrichtlinien konfigurieren möchten. 
  
### <a name="add-storage-databases-to-your-topology"></a>Hinzufügen von Speicherdatenbanken zu Ihrer Topologie

Beim Hinzufügen von SQL Server-Speicher-Datenbanken zu Ihrer Topologie können Sie die Archivierungsdatenbanken mit einem der folgenden zusammenstellen:
  
- Überwachungsdatenbank
    
- Back-End-Datenbank eines Enterprise Edition-Front-End-Pools
    
> [!NOTE]
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden. 
  
Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, Back-End-Datenbank oder beide Datenbanken zusammenstellen, Sie können entweder eine einzelne Instanz von SQL für einige oder alle Datenbanken verwenden, oder Sie können eine eigene SQL-Instanz verwenden, für jede Datenbank, mit der folgenden Einschränkung: jede SQL-Instanz kann nur eine einzige Back-End-Datenbank, die Überwachungsdatenbank und die einzige Archivierungsdatenbank enthalten.
  
Ausführliche Informationen zum Verbinden aller Serverrollen und Datenbanken finden Sie unter [Grundlagen der Topologie Skype für Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Ausführliche Informationen zum Aktualisieren Ihrer Topologie zum Einschließen von Speichergruppen Datenbanken finden Sie unter [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Festlegen von Archivierungsoptionen und Benutzerrichtlinien

Sie müssen folgendes festlegen:
  
- Aktivierung oder Deaktivierung der Archivierung für die interne und externe Kommunikation
    
- Zu archivierende Elemente (Chatnachrichten, Konferenzen oder beides)
    
- Ob kritischen Modus implementiert die im- und konferenzsitzungen im Fall eines WAN-einen Skype für Business Serverausfall blockiert 
    
- Aktivierung von Richtlinien für bestimmte Benutzer und Benutzergruppen
    
Skype für Business-Archivierungsoptionen kann auf folgenden Ebenen angegeben werden. 
  
- **Globale Option Ebene**. Dies ist die Standardeinstellung Archivierungskonfiguration und gilt für die gesamte Bereitstellung. Es wird bei der Bereitstellung von Skype für Business Server erstellt und standardmäßig deaktiviert die Archivierung für interne und externe Kommunikation. Diese Option kann nicht gelöscht werden. Wenn Sie die Option zum Löschen auswählen, wird die globale Option auf die Standardeinstellungen zurückgesetzt.
    
- **Standortebene**. Sie können die Archivierung für einen oder mehrere bestimmte Standorte aktivieren oder deaktivieren, wenn Sie jeweils eine Archivierungsoption erstellen und konfigurieren. Jede selbst erstellte Archivierungsoption auf Standortebene kann gelöscht werden. Eine Archivierungsoption auf Standortebene hat Vorrang vor der globalen Option, jedoch nur für den in der Option angegebenen Standort. 
    
    Wenn Sie beispielsweise die Archivierung für die interne und die externe Kommunikation in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung für die externe Kommunikation deaktivieren, wird nur die interne Kommunikation für diesen Standort archiviert. Wenn Sie, als weiteres Beispiel, die Archivierung in Ihrer globalen Konfiguration nur für Chatnachrichten aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung sowohl für Chatnachrichten als auch für Konferenzen aktivieren, werden nur die Konferenzen für den Standort archiviert, nicht für den Rest Ihrer Organisation.
    
- **Poolebene**. Sie können die Archivierungseinstellungen für einen oder mehrere bestimmte Pools festlegen, wenn Sie jeweils eine Konfiguration auf Poolebene erstellen und konfigurieren. Eine Archivierungskonfiguration auf Poolebene ist nur vorhanden, wenn Sie sie erstellen. Jede selbst erstellte Archivierungskonfiguration auf Poolebene kann gelöscht werden. Eine Archivierungskonfiguration auf Poolebene hat Vorrang vor der globalen Konfiguration und jeder Standortarchivierungskonfiguration, die Sie eventuell erstellt haben. 
    
    Beispiel: Sie aktivieren die Archivierung für Chatsitzungen nur in Ihrer globalen Konfiguration, erstellen dann eine Konfiguration auf Standortebene, in der Sie die Archivierung sowohl für Chat- als auch für Webkonferenzsitzungen aktivieren, und erstellen anschließend eine Konfiguration auf Poolebene, in der Sie nur die Archivierung von Chatsitzungen aktivieren. In dieser Konstellation würde die Kommunikation sowohl für Chatsitzungen als auch für Webkonferenzsitzungen für alle Benutzer des Standorts archiviert, nicht jedoch für Benutzer, die in dem Pool verwaltet werden, der in der Konfiguration für die Poolebene angegeben ist. Für alle anderen Benutzer in Ihrer Organisation würden nur Chatsitzungen archiviert werden.
    
- **Archivierungsrichtlinien für Benutzer**. Sie können die Archivierung für einen oder mehrere bestimmte Benutzer und Benutzergruppen aktivieren oder deaktivieren, indem Sie für diese eine Archivierungsrichtlinie auf Benutzerebene erstellen, konfigurieren und anwenden. Sie können jede Archivierungsrichtlinie auf Benutzerebene löschen und Sie können ändern, für welche Benutzer und Benutzergruppen die Archivierungsrichtlinie gelten soll. Eine Archivierungsrichtlinie auf Benutzerebene hat Vorrang vor der globalen Richtlinie und allen Standortrichtlinien, jedoch nur für die Benutzer und Benutzergruppen, für die die Richtlinie gilt. 
    
    Angenommen, Sie Deaktivieren der Archivierung für interne und externe Kommunikation in Ihrer globale Konfiguration, erstellen eine Richtlinie auf Standortebene, in dem Sie die Archivierung für die internen und externen Kommunikation aktivieren, und klicken Sie dann eine Richtlinie auf Benutzerebene erstellen, in dem Sie Deaktivieren der Archivierung für externe Kommunikation. Kommunikation würde für die externe und interne Kommunikation für alle Benutzer mit Ausnahme der Benutzer der Website archiviert werden, die Sie die Richtlinie auf Benutzerebene – für diese Benutzer anwenden, die nur interne Kommunikation archiviert werden würde.
    
Ausführliche Informationen zum erstmaligen Archivierung Konfiguration einrichten, bei der Bereitstellung von Archivierung finden Sie unter [Archivierung für Skype für Business Server bereitstellen](../../deploy/deploy-archiving/deploy-archiving.md). Ausführliche Informationen zum Verwalten der Archivierung nach der Bereitstellung finden Sie unter [Verwalten der Archivierung in Skype für Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Archivierungskonfigurationstools

 Sie haben die meisten Archivierungsoptionen mithilfe von der Skype Business Server-Systemsteuerung steuern. Es gibt jedoch einige Optionen zur Verfügung nur mithilfe der Skype für Business Server-Verwaltungsshell. Zu diesen Optionen zählen die Archivierung von Nachrichtenduplikaten und der Export archivierter Daten. Weitere Informationen zur Verwendung der Skype für Business Server-Systemsteuerung und die Skype für Business Server-Verwaltungsshell zum Verwalten von Archivierungsrichtlinien finden Sie unter [Verwalten der Archivierung in Skype für Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Zugriff auf archivierte Daten

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden: 
  
- **Microsoft Exchange-Speicher**. Wenn Sie die Exchange-Integration-Option auswählen, legt Skype für Business Server die archivierten Inhalte im Exchange-Speicher für alle Benutzer, die in Exchange verwaltet werden und wer hatten ihren Postfächern Compliance-Archiv zu platzieren. Archivierte Daten werden in des Ordners wiederherstellbare Elemente der Postfächer für Benutzer gespeichert, der in der Regel für Benutzer nicht sichtbar ist, und kann nur von Benutzern mit einer Rolle Exchange **Discoveryverwaltung** durchsucht werden. Exchange aktiviert Sammelsuche und Erkennung, zusammen mit SharePoint, wenn sie bereitgestellt wird. Weitere Informationen zur Speicherung, Archivierung und Suche von Daten in Exchange gespeichert finden Sie in der Dokumentation zu Exchange und SharePoint.
    
- **Skype als Archivierungsspeicher Business Server**. Wenn Sie Skype für Business Server-Archivierungsdatenbanken eingerichtet haben, Skype für Business Server bandbreitenbeschränkungen nicht Archivierung von Inhalten in der Skype für Business Server-Archivierungsdatenbanken für jeden Benutzer, der in Exchange verwaltet und hatten, die nicht ihren Postfächern Compliance-Archiv zu platzieren. This data is not searchable, but it can be exported to formats that are searchable using other tools. Ausführliche Informationen zum Exportieren von Daten in Archivierungsdatenbanken finden Sie unter [Exportieren von archivierten Daten in Skype für Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zur Archivierung finden Sie in den folgenden Themen:
  
- [Bereitstellung einer Archivierung für Skype für Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Verwalten der Archivierung in Skype für Business Server](../../manage/archiving/archiving.md)
    
Weitere Informationen dazu, wie Sie Skype Business Server und Exchange, zusammenarbeiten, finden Sie unter [Planen der Integration von Skype für Unternehmen und Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

