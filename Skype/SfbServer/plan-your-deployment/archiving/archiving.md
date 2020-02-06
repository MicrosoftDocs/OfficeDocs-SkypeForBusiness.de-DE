---
title: Planen der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Archivierung in Skype for Business Server planen.'
ms.openlocfilehash: 92658ef139464cacaa7f66abb2cf3aa6294b463b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816084"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planen der Archivierung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung in Skype for Business Server planen.
  
Unternehmen und andere Organisationen müssen eine zunehmende Anzahl von Rechtsvorschriften beachten, die die Speicherung bestimmter Kommunikationsarten erfordern. Wenn in Ihrer Organisation derartige Anforderungen erfüllt sind, können Sie die Archivierung in Skype for Business Server verwenden, um Chatnachrichten und Konferenzen (Besprechungen) zu archivieren, um einige Ihrer Compliance-Anforderungen zu unterstützen.
  
## <a name="archiving-components"></a>Archivierungskomponenten

Skype for Business Server verwendet die folgenden Archivierungskomponenten:
  
- **Archivierungs-Agents**. Archivierungs-Agents (die auch als einheitliche Datenerfassungs-Agents bezeichnet werden) werden automatisch in jedem Enterprise Edition-Front-End-Pool und auf jedem Standard Edition-Server installiert und aktiviert. Auch wenn die Archivierungs-Agents automatisch aktiviert werden, werden Nachrichten erst dann erfasst, wenn die Archivierung aktiviert und entsprechend konfiguriert wurde. Standardmäßig ist die Archivierung deaktiviert.
    
- **Archivierungsdatenspeicher**. Die Datenspeicherung für Skype for Business Server kann als Skype for Business Server-SQL Server-Datenbanken oder, wenn Sie über eine Exchange-Bereitstellung verfügen, in den Exchange-Speicher integriert werden. 
    
Die Archivierung erfordert auch Dateispeicher. Es wird jedoch der gleiche Dateispeicher wie für Front-End- und Standard Edition-Server verwendet.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Bestimmen der Archivierungsanforderungen Ihrer Organisation

Um die Archivierung zu implementieren, müssen Sie entscheiden, wie Sie die Anforderungen Ihrer Organisation für die Archivierung erfüllen möchten, indem Sie Folgendes ermitteln:
  
- **Wahl der richtigen Speicheroption**. Es gibt zwei Möglichkeiten, Speicher zu implementieren (Sie können auch eine Kombination aus beiden verwenden):
    
  - **Exchange-Speicher.** Wenn Sie über eine Exchange-Bereitstellung verfügen, können Sie die Skype for Business Server-und Exchange-Archivierung integrieren, damit Ihr Skype for Business-Server und die archivierten Exchange-Daten in Exchange zusammen gespeichert werden. Wenn Sie die Microsoft Exchange-Integrations Option aktivieren, verwenden Benutzerpostfächer, die auf dem Exchange-Server gespeichert sind, den Exchange-Speicher für archivierte Daten, jedoch nur, wenn die Postfächer in-situ-Speicher abgelegt wurden. Standardmäßig ist die Microsoft Exchange-Integration nicht aktiviert.
    
  - **Skype for Business Server-Speicher.** Wenn Sie über Benutzer verfügen, die nicht in Exchange gespeichert sind oder deren Postfächer nicht in einem Speicherplatz vorhanden sind, oder wenn Sie die Microsoft Exchange-Integration nicht für einen oder alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie Skype for Business Server-Archivierungsdatenbanken mithilfe von S bereitstellen. QL-Server.
    
- **Zeitpunkt der Archivierungsbereitstellung.** Sie können die Archivierung im Rahmen ihrer anfänglichen Skype for Business Server-Bereitstellung bereitstellen, oder Sie können Sie einer vorhandenen Bereitstellung hinzufügen. Wenn Sie den Skype for Business Server-Archivierungsspeicher (SQL Server-Datenbanken) verwenden möchten, fügen Sie die Datenbanken mithilfe des Topologie-Generators Ihrer Topologie hinzu, und veröffentlichen Sie die Topologie dann erneut. Wenn alle Ihre Benutzer in Exchange gespeichert sind und ihre Postfächer in-situ-Speicher abgelegt werden, müssen Sie Ihre Topologie nicht aktualisieren, müssen aber nur die Microsoft Exchange-Integration aktivieren, um archivierte Daten in Exchange zu speichern. 
    
- **Standorte und Benutzer in der Organisation, die eine Archivierung benötigen**. Sie können Archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Websites, Pools, Benutzer und Benutzergruppen konfigurieren.
    
- **Archivierungsinhalte**. Soll die Archivierung auf globaler Ebene oder für bestimmte Standorte und Benutzer durchgeführt werden, müssen sie für jede dieser Ebenen festlegen, ob die folgenden Arten von Inhalten aktiviert werden sollen oder nicht: 
    
  - Peer-zu-Peer-Chatnachrichten
    
  - Konferenzen (Besprechungen), die Teil von Chatsitzungen mit mehreren Teilnehmern sind
    
  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)
    
  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz
    
- **Nicht archivierbare Inhalte**. Die folgenden Arten von Inhalten können nicht archiviert werden: 
    
  - Peer-to-Peer-Dateiübertragungen
    
  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen
    
  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Chatnachrichten und -konferenzen
    
    Skype for Business Server archiviert auch keine beständigen Chat Unterhaltungen. Zum Archivieren beständiger Chat Unterhaltungen müssen Sie den Kompatibilitätsdienst aktivieren und konfigurieren, bei dem es sich um eine Komponente handelt, die mit dem Server für beständigen Chat bereitgestellt werden kann. Ausführliche Informationen finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
    
- **Dauer der Aufbewahrung archivierter Daten**. Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine e-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in andere Speicher verschoben werden müssen. Skype for Business Server bietet ein Sitzungs Export Tool, mit dem Sie archivierte Daten exportieren und durchsuchbare Transkripte der archivierten Daten erstellen können. 
    
     Für die globale Richtlinie und für jede von Ihnen erstellte Website-und Benutzerrichtlinie können Sie angeben, wann Archivierte und exportierte Daten bereinigt werden sollen. Weitere Informationen zum Löschen von Daten finden Sie unter [Verwalten der Bereinigung archivierter Daten in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Weitere Informationen zum Verwenden des Sitzungs Exporttools finden Sie unter [Exportieren von archivierten Daten in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Archivierung der internen oder externen Kommunikation**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (Kommunikationen, an denen mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    > [!NOTE]
    > Die Steuerung der Archivierung für die interne oder externe Kommunikation ist nur für die Skype for Business-Richtlinie verfügbar. Für die Exchange-integrierte Archivierung werden sowohl die interne als auch die externe Kommunikation entweder archiviert oder nicht archiviert. 
  
- **Implementierung des kritischen Modus**. Wenn die Archivierung eine Voraussetzung für Ihre Organisation ist, blockiert die Konfiguration des kritischen Modus Chat-und Konferenzsitzungen im Fall eines Skype for Business-Server Fehlers, der die Archivierung verhindert. Beispiel: 
    
  - Ein Problem mit dem Speicherdienst von Skype for Business Server. In diesem Fall werden Chatnachrichten für Benutzer blockiert, für die die Archivierung aktiviert wurde.
    
  - Eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst. In diesem Fall werden aktive Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet und neue Konferenzen können nicht aktiviert werden.
    
    Chatnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Auswählen der Archivierungsbereitstellung und Konfigurationsoptionen

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert. Die Konfiguration der Archivierung ist dabei abhängig von Ihrer Bereitstellung. Es gibt mehrere Möglichkeiten, die Archivierung bereitzustellen:
  
- Verwenden des Microsoft Exchange-Speichers
    
- Verwenden von Skype for Business Server-Speicher
    
> [!NOTE]
> Wenn Sie sowohl Skype for Business Server-Archivierungsdatenbanken implementieren als auch die Microsoft Exchange-Integration aktivieren, setzen Exchange-Richtlinien die Archivierungsrichtlinien für Skype for Business Server außer Kraft, jedoch nur für Benutzer, die sich in Exchange befinden und ihre Postfächer aktiviert haben. In-situ-Speicher. Die Archivierung von Skype for Business hängt von der Microsoft Exchange-Richtlinie für den in-situ-Speicher ab. 
  
Wenn Sie die Archivierung für einen Front-End-Pool oder Standard Edition-Server bereitstellen, sollten Sie Sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren. Wenn die Archivierung nicht auf dem Pool aktiviert wird, auf dem eine Unterhaltung oder Besprechung verwaltet wird, können keine Konferenzdaten archiviert werden. Die Archivierung funktioniert zwar noch für Chatnachrichten, aber Konferenzinhalte und -ereignisse können nicht archiviert werden.
  
> [!NOTE]
> Um die Delegierung von administrativen Aufgaben unter Beibehaltung der Sicherheitsstandards Ihrer Organisation zu aktivieren, verwendet Skype for Business Server die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC). Bei der rollenbasierten Zugriffssteuerung werden Administratorrechte zugewiesen, indem Benutzer vordefinierten Administrationsrollen hinzugefügt werden. Um Skype for Business-Archivierungsrichtlinien und-Konfigurationen zu konfigurieren, muss der Benutzer der CsArchivingAdministrator-Rolle zugewiesen werden (es sei denn, die Konfiguration erfolgt direkt auf dem Server, auf dem die Archivierung statt Remote von einem anderen Computer ausgeführt wird. ). Eine Liste der Benutzerrechte, Berechtigungen und Rollen, die für die Archivierungs Bereitstellung erforderlich sind, finden Sie unter [Bereitstellen der Archivierung für Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration verwenden, erfordert die Konfiguration von Exchange-Richtlinien geeignete Administratorrechte und-Berechtigungen. Ausführliche Informationen finden Sie in der Exchange-Dokumentation. 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher

 Wenn Sie die Microsoft Exchange-Integration auswählen, verwenden Sie Exchange-Richtlinien und-Konfigurationen, um die Archivierung von Skype for Business Server zu steuern. Sie können die Microsoft Exchange-Integrations Option auf globaler Ebene, Websiteebene und Poolebene konfigurieren. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen Skype for Business Server und Exchange synchronisieren. Außerdem müssen Sie folgendes festlegen:
  
- Zu archivierende Elemente (Chatnachrichten, Konferenzen oder beides)
    
- Ob kritischer Modus implementiert wird, der Chat-und Konferenzsitzungen blockiert, wenn ein Skype for Business-Server Fehler auftritt 
    
- Auswahl der Microsoft Exchange-Integrations Option für die Verwendung von Exchange für die Speicherung archivierter Daten
    
Informationen zum Konfigurieren von Exchange in-situ-Speicherrichtlinien und-Einstellungen zur Unterstützung der Archivierung finden Sie in der Exchange-Produktdokumentation.
  
### <a name="skype-for-business-server-storage"></a>Speicher in Skype for Business Server

Wenn Sie den Skype for Business Server-Speicher wählen, verwenden Sie die Archivierungsrichtlinien und-Konfigurationen von Skype for Business Server, um zu steuern, wie die Archivierung aktiviert und implementiert wird. Da Skype for Business Server-Speicher SQL Server-Datenbanken verwendet, müssen Sie Ihrer Topologie die entsprechenden SQL Server-Datenbanken hinzufügen und dann Ihre Archivierungsrichtlinien konfigurieren. 
  
### <a name="add-storage-databases-to-your-topology"></a>Hinzufügen von Speicherdatenbanken zu Ihrer Topologie

Beim Hinzufügen von SQL Server-Speicher Datenbanken zu Ihrer Topologie können Sie die Archivierungsdatenbanken mit einer der folgenden collocate:
  
- Überwachungsdatenbank
    
- Back-End-Datenbank eines Enterprise Edition-Front-End-Pools
    
> [!NOTE]
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden. 
  
Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder beider Datenbanken collocate, können Sie entweder eine einzelne SQL-Instanz für eine oder alle Datenbanken verwenden, oder Sie können für jede Datenbank eine separate SQL-Instanz verwenden, mit den folgenden Einschränkung: jede SQL-Instanz kann nur eine einzige Back-End-Datenbank, eine einzige Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.
  
Ausführliche Informationen zur Anordnung aller Serverrollen und Datenbanken finden Sie unter [Topologie-Grundlagen für Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Details zum Aktualisieren Ihrer Topologie auf die Speicherung von Datenbanken finden Sie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Festlegen von Archivierungsoptionen und Benutzerrichtlinien

Sie müssen folgendes festlegen:
  
- Aktivierung oder Deaktivierung der Archivierung für die interne und externe Kommunikation
    
- Zu archivierende Elemente (Chatnachrichten, Konferenzen oder beides)
    
- Ob kritischer Modus implementiert wird, der Chat-und Konferenzsitzungen blockiert, wenn ein Skype for Business-Server Fehler auftritt 
    
- Aktivierung von Richtlinien für bestimmte Benutzer und Benutzergruppen
    
Die Archivierungsoptionen für Skype for Business Server können auf den folgenden Ebenen angegeben werden. 
  
- **Option "globale Ebene"**. Hierbei handelt es sich um die standardmäßige Archivierungskonfiguration, die auf die gesamte Bereitstellung angewendet wird. Sie wird bei der Bereitstellung von Skype for Business Server erstellt und deaktiviert standardmäßig die Archivierung für die interne und externe Kommunikation. Diese Option kann nicht gelöscht werden. Wenn Sie die Option "Löschen" auswählen, wird die globale Option auf die Standardeinstellungen zurückgesetzt.
    
- **Standortebene**. Sie können die Archivierung für einen oder mehrere bestimmte Standorte aktivieren oder deaktivieren, wenn Sie jeweils eine Archivierungsoption erstellen und konfigurieren. Jede selbst erstellte Archivierungsoption auf Standortebene kann gelöscht werden. Eine Archivierungsoption auf Standortebene hat Vorrang vor der globalen Option, jedoch nur für den in der Option angegebenen Standort. 
    
    Wenn Sie beispielsweise die Archivierung für die interne und die externe Kommunikation in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung für die externe Kommunikation deaktivieren, wird nur die interne Kommunikation für diesen Standort archiviert. Wenn Sie, als weiteres Beispiel, die Archivierung in Ihrer globalen Konfiguration nur für Chatnachrichten aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung sowohl für Chatnachrichten als auch für Konferenzen aktivieren, werden nur die Konferenzen für den Standort archiviert, nicht für den Rest Ihrer Organisation.
    
- **Poolebene**. Sie können die Archivierungseinstellungen für einen oder mehrere bestimmte Pools festlegen, wenn Sie jeweils eine Konfiguration auf Poolebene erstellen und konfigurieren. Eine Archivierungskonfiguration auf Poolebene ist nur vorhanden, wenn Sie sie erstellen. Jede selbst erstellte Archivierungskonfiguration auf Poolebene kann gelöscht werden. Eine Archivierungskonfiguration auf Poolebene hat Vorrang vor der globalen Konfiguration und jeder Standortarchivierungskonfiguration, die Sie eventuell erstellt haben. 
    
    Beispiel: Sie aktivieren die Archivierung für Chatsitzungen nur in Ihrer globalen Konfiguration, erstellen dann eine Konfiguration auf Standortebene, in der Sie die Archivierung sowohl für Chat- als auch für Webkonferenzsitzungen aktivieren, und erstellen anschließend eine Konfiguration auf Poolebene, in der Sie nur die Archivierung von Chatsitzungen aktivieren. In dieser Konstellation würde die Kommunikation sowohl für Chatsitzungen als auch für Webkonferenzsitzungen für alle Benutzer des Standorts archiviert, nicht jedoch für Benutzer, die in dem Pool verwaltet werden, der in der Konfiguration für die Poolebene angegeben ist. Für alle anderen Benutzer in Ihrer Organisation würden nur Chatsitzungen archiviert werden.
    
- **Archivierungsrichtlinien für Benutzer**. Sie können die Archivierung für einen oder mehrere bestimmte Benutzer und Benutzergruppen aktivieren oder deaktivieren, indem Sie für diese eine Archivierungsrichtlinie auf Benutzerebene erstellen, konfigurieren und anwenden. Sie können jede Archivierungsrichtlinie auf Benutzerebene löschen und Sie können ändern, für welche Benutzer und Benutzergruppen die Archivierungsrichtlinie gelten soll. Eine Archivierungsrichtlinie auf Benutzerebene hat Vorrang vor der globalen Richtlinie und allen Standortrichtlinien, jedoch nur für die Benutzer und Benutzergruppen, für die die Richtlinie gilt. 
    
    Angenommen, Sie deaktivieren die Archivierung für die interne und externe Kommunikation in ihrer globalen Konfiguration, erstellen eine Richtlinie auf Websiteebene, in der Sie die Archivierung für die interne und externe Kommunikation aktivieren, und erstellen dann eine Richtlinie auf Benutzerebene, in der Sie Deaktivieren Sie die Archivierung für die externe Kommunikation. Die Kommunikation für alle Websitebenutzer wird sowohl für die externe als auch für die interne Kommunikation archiviert, mit Ausnahme der Benutzer, denen Sie die Richtlinie auf Benutzerebene zuweisen – für diese Benutzer wird nur die interne Kommunikation archiviert.
    
Details zum Einrichten von anfänglichen Archivierungs Konfigurationen beim Bereitstellen der Archivierung finden Sie unter [Bereitstellen der Archivierung für Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Details zum Verwalten der Archivierung nach der Bereitstellung finden Sie unter [Verwalten der Archivierung in Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Archivierungskonfigurationstools

 Sie können die meisten Archivierungsoptionen über die Skype for Business Server-Systemsteuerung steuern. Es gibt jedoch einige Optionen, die nur über die Skype for Business Server-Verwaltungsshell zur Verfügung stehen. Zu diesen Optionen zählen die Archivierung von Nachrichtenduplikaten und der Export archivierter Daten. Weitere Informationen zur Verwendung des Skype for Business Server-Control Panels und der Skype for Business Server-Verwaltungsshell zum Verwalten von Archivierungsrichtlinien finden Sie unter [Verwalten der Archivierung in Skype for Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Zugriff auf archivierte Daten

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden: 
  
- **Microsoft Exchange-Speicher**. Wenn Sie die Option für die Exchange-Integration auswählen, gibt Skype for Business Server den Archivierungs Inhalt im Exchange-Informationsspeicher für alle Benutzer aus, die sich in Exchange befinden und deren Postfächer in den Wartebereich gesetzt wurden. Archivierte Daten werden im Ordner "Wiederherstellbare Elemente" der Benutzerpostfächer gespeichert, der für Benutzer in der Regel nicht sichtbar ist und nur von Benutzern mit einer Exchange **Discovery-Verwaltungs** Rolle durchsucht werden kann. Exchange ermöglicht die Verbundsuche und-Erkennung zusammen mit SharePoint, wenn Sie bereitgestellt wird. Weitere Informationen zum Speichern, zur Aufbewahrung und zur Erkennung von Daten, die in Exchange gespeichert sind, finden Sie in der Dokumentation zu Exchange und SharePoint.
    
- **Skype for Business Server-Archivierungsspeicher**. Wenn Sie Skype for Business Server-Archivierungsdatenbanken einrichten, werden von Skype for Business Server Archivierungs Inhalte in den Skype for Business Server-Archivierungsdatenbanken für alle Benutzer gespeichert, die sich nicht in Exchange befinden und deren Postfächer nicht in den Speicherplatz gesetzt wurden. Diese Daten sind nicht durchsuchbar, können aber in Formate exportiert werden, die mit anderen Tools durchsucht werden können. Informationen zum Exportieren von Daten, die in Archivierungsdatenbanken gespeichert sind, finden Sie unter [Exportieren von archivierten Daten in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zur Archivierung finden Sie in den folgenden Themen:
  
- [Bereitstellen der Archivierung für Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Verwalten der Archivierung in Skype for Business Server](../../manage/archiving/archiving.md)
    
Weitere Informationen dazu, wie Skype for Business Server und Exchange zusammenarbeiten, finden Sie unter [Planen der Integration von Skype for Business und Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

