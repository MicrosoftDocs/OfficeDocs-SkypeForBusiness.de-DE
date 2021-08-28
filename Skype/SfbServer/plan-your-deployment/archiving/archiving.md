---
title: Planen der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Archivierung in Skype for Business Server planen.'
ms.openlocfilehash: e9ebe5aa0b2e4e84d436d24f9d8b7db3b450825d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629577"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planen der Archivierung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung in Skype for Business Server planen.
  
Unternehmen und andere Organisationen müssen eine zunehmende Anzahl von Rechtsvorschriften beachten, die die Speicherung bestimmter Kommunikationsarten erfordern. Wenn Ihre Organisation solche Anforderungen hat, können Sie die Archivierung in Skype for Business Server verwenden, um Chatnachrichten und Konferenzkommunikationen (Besprechungen) zu archivieren, um einige Ihrer Complianceanforderungen zu unterstützen.
  
## <a name="archiving-components"></a>Archivierungskomponenten

Skype for Business Server verwendet die folgenden Archivierungskomponenten:
  
- **Archivierungs-Agents**. Archivierungs-Agents (auch als einheitliche Datensammlungs-Agents bezeichnet) werden automatisch auf jedem Enterprise Edition Front-End-Pool und Standard Edition Server installiert und aktiviert. Obwohl Archivierungs-Agents automatisch aktiviert werden, werden keine Nachrichten erfasst, bis die Archivierung aktiviert und entsprechend konfiguriert ist. Standardmäßig ist die Archivierung deaktiviert.
    
- **Datenspeicher für die Archivierung**. Der Datenspeicher für Skype for Business Server kann als Skype for Business Server SQL Server Datenbanken implementiert werden oder, wenn Sie über eine Exchange Bereitstellung verfügen, in Exchange Speicher integriert werden. 
    
Die Archivierung erfordert auch dateispeicherung, aber die Archivierung verwendet den gleichen Dateispeicher wie die Front-End-Server oder Standard Edition Server.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Ermitteln der Anforderungen Ihrer Organisation für die Archivierung

Um die Archivierung zu implementieren, müssen Sie entscheiden, wie die Archivierungsanforderungen Ihrer Organisation erfüllt werden sollen, indem Sie Folgendes festlegen:
  
- **Welche Speicheroption verwendet werden soll.** Sie können Speicher auf eine von zwei Arten implementieren oder eine Kombination aus beiden verwenden:
    
  - **Exchange Speicher.** Wenn Sie über eine Exchange Bereitstellung verfügen, können Sie Skype for Business Server und Exchange Archivierung integrieren, sodass Ihre Skype for Business Server und Exchange archivierten Daten in Exchange gespeichert werden. Wenn Sie die Integrationsoption "Microsoft Exchange" aktivieren, verwenden benutzerpostfächer, die im Exchange Server verwaltet werden, Exchange Speicher für archivierte Daten, jedoch nur, wenn die Postfächer in In-Place Haltebereich gesetzt wurden. Standardmäßig ist die Integration von Microsoft Exchange nicht aktiviert.
    
  - **Skype for Business Server Speicher.** Wenn Sie Benutzer haben, die nicht in Exchange verwaltet werden oder für die ihre Postfächer nicht In-Place Aufbewahrung aktiviert wurden, oder wenn Sie microsoft Exchange Integration für einen oder alle Benutzer in Ihrer Bereitstellung nicht verwenden möchten, können Sie Skype for Business Server Archivierungsdatenbanken mit SQL Server bereitstellen.
    
- **Wann soll die Archivierung bereitgestellt werden?** Sie können die Archivierung als Teil Ihrer anfänglichen Skype for Business Server Bereitstellung bereitstellen oder sie einer vorhandenen Bereitstellung hinzufügen. Um Skype for Business Server Archivierungsspeicher (SQL Server Datenbanken) zu verwenden, verwenden Sie den Topologie-Generator, um die Datenbanken zu Ihrer Topologie hinzuzufügen und die Topologie dann erneut zu veröffentlichen. Wenn alle Ihre Benutzer in Exchange verwaltet werden und ihre Postfächer in In-Place Haltebereich gesetzt werden, müssen Sie Ihre Topologie nicht aktualisieren, sondern nur die Integration von Microsoft Exchange aktivieren, um archivierte Daten in Exchange zu speichern. 
    
- **Welche Standorte und Benutzer in der Organisation eine Archivierung benötigen.** Sie können Archivierungseinstellungen für Ihre gesamte Organisation und optional für bestimmte Standorte, Pools, Benutzer und Benutzergruppen konfigurieren.
    
- **Welche Inhalte archiviert werden sollen.** Unabhängig davon, ob Sie die Archivierung auf globaler Ebene oder für bestimmte Standorte und Benutzer auf jeder dieser Ebenen angeben, geben Sie an, ob die folgenden Inhaltstypen aktiviert werden sollen: 
    
  - Peer-zu-Peer-Sofortnachrichten
    
  - Konferenzen (Besprechungen), die Teil von Sofortnachrichtensitzungen mit mehreren Teilnehmern sind
    
  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)
    
  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz
    
- **Welche Inhalte können nicht archiviert werden.** Die folgenden Inhaltstypen können nicht archiviert werden: 
    
  - Peer-zu-Peer-Dateiübertragungen
    
  - Audio-/Videoinhalte für Peer-zu-Peer-Sofortnachrichten und -konferenzen
    
  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Sofortnachrichten und -konferenzen
    
    Skype for Business Server archiviert auch keine Unterhaltungen im beständigen Chat. Zum Archivieren von Unterhaltungen für beständigen Chat müssen Sie den Konformitätsdienst aktivieren und konfigurieren, der eine Komponente ist, die mit dem Server für beständigen Chat bereitgestellt werden kann. Ausführliche Informationen finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 
    
- **Wie lange archivierte Materialien aufbewahrt werden sollen.** Die Archivierungsdatenbank ist nicht für die langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine E-Discovery-Lösung (Suche) für archivierte Daten, sodass Daten in einen anderen Speicher verschoben werden müssen. Skype for Business Server stellt ein Sitzungsexporttool bereit, das Sie zum Exportieren archivierter Daten verwenden können und das durchsuchbare Transkripte der archivierten Daten erstellt. 
    
     Für die globale Richtlinie und für jede Website- und Benutzerrichtlinie, die Sie erstellen, können Sie angeben, wann archivierte und exportierte Daten gelöscht werden sollen. Weitere Informationen zum Löschen von Daten finden Sie unter [Verwalten des Löschens archivierter Daten in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Weitere Informationen zur Verwendung des Sitzungsexporttools finden Sie unter [Exportieren archivierter Daten in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
- **Ob die interne oder externe Kommunikation archiviert werden soll**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (die Kommunikation, bei der mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    > [!NOTE]
    > Die Steuerung der Archivierung für die interne oder externe Kommunikation ist nur für Skype for Business Richtlinie verfügbar. Für Exchange-integrierte Archivierung werden sowohl die interne als auch die externe Kommunikation archiviert oder nicht archiviert. 
  
- **Gibt an, ob der kritische Modus implementiert werden soll.** Wenn die Archivierung eine Anforderung für Ihre Organisation ist, blockiert das Konfigurieren des kritischen Modus Chat- und Konferenzsitzungen im Falle eines Skype for Business Server Fehlers, der die Archivierung verhindern würde. Zum Beispiel: 
    
  - Ein Problem mit dem Skype for Business Server-Speicherdienst. In diesem Fall wird Chat für Benutzer blockiert, die für die Archivierung aktiviert sind.
    
  - Eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Auswählen von Archivierungsbereitstellungs- und Konfigurationsoptionen

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert, die Archivierung ist jedoch erst aktiviert, nachdem Sie sie konfiguriert haben. Wie Sie die Archivierung konfigurieren, hängt davon ab, wie Sie sie bereitstellen. Sie können die Archivierung auf eine der folgenden Arten bereitstellen:
  
- Verwenden von Microsoft Exchange-Speicher
    
- Verwenden Skype for Business Server Speichers
    
> [!NOTE]
> Wenn Sie sowohl Skype for Business Server Archivierungsdatenbanken implementieren als auch die Integration von Microsoft Exchange aktivieren, setzen Exchange Richtlinien Skype for Business Server Archivierungsrichtlinien außer Kraft, jedoch nur für Benutzer, die in Exchange verwaltet werden und deren Postfächer in In-Place Haltebereich gesetzt wurden. Skype for Business Archivierung hängt von der Microsoft Exchange In-Place-Aufbewahrungsrichtlinie ab. 
  
Wenn Sie die Archivierung für einen Front-End-Pool oder Standard Edition Server bereitstellen, sollten Sie sie für alle anderen Front-End-Pools und Standard Edition Server in Ihrer Bereitstellung aktivieren. Wenn die Archivierung in dem Pool, in dem eine Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, werden möglicherweise nicht alle Konferenzdaten archiviert. Die Archivierung funktioniert weiterhin für Chatnachrichten, konferenzbezogene Inhalte und Ereignisse werden jedoch möglicherweise nicht archiviert.
  
> [!NOTE]
> Um die Delegierung administrativer Aufgaben unter Beibehaltung der Sicherheitsstandards Ihrer Organisation zu aktivieren, verwendet Skype for Business Server die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC). Mit RBAC werden Administratorrechte gewährt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden. Um Skype for Business Archivierungsrichtlinien und -konfigurationen zu konfigurieren, muss der Benutzer der Rolle "CsArchivingAdministrator" zugewiesen werden (es sei denn, die Konfiguration erfolgt direkt auf dem Server, auf dem die Archivierung bereitgestellt wird, und nicht remote von einem anderen Computer aus). Eine Liste der für die Archivierungsbereitstellung erforderlichen Benutzerrechte, Berechtigungen und Rollen finden Sie unter [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Wenn Sie Microsoft Exchange Integration verwenden, erfordert die Konfiguration von Exchange Richtlinien die entsprechenden Administratorrechte und Berechtigungen. Ausführliche Informationen finden Sie in der Exchange Dokumentation. 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher

 Wenn Sie microsoft Exchange Integration auswählen, verwenden Sie Exchange Richtlinien und Konfigurationen, um die Archivierung von Skype for Business Server zu steuern. Sie können die Microsoft Exchange-Integrationsoption auf globaler, Standort- und Poolebene konfigurieren. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen Skype for Business Server und Exchange synchronisieren. Sie müssen Folgendes ermitteln:
  
- Ob Chats, Konferenzen oder beides archiviert werden sollen
    
- Gibt an, ob der kritische Modus implementiert werden soll, der Chat- und Konferenzsitzungen bei einem Skype for Business Server Fehler blockiert. 
    
- Auswahl der Microsoft Exchange-Integrationsoption zur Verwendung von Exchange zum Speichern archivierter Daten
    
Informationen zum Konfigurieren Exchange In-Place Aufbewahrungsrichtlinien und -einstellungen zur Unterstützung der Archivierung finden Sie in der Exchange Produktdokumentation.
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server Speicher

Wenn Sie Skype for Business Server Speicher auswählen, verwenden Sie Skype for Business Server Archivierungsrichtlinien und -konfigurationen, um zu steuern, wie die Archivierung aktiviert und implementiert wird. Skype for Business Server Speicher SQL Server Datenbanken verwendet, müssen Sie daher die entsprechenden SQL Server Datenbanken zu Ihrer Topologie hinzufügen und dann Ihre Archivierungsrichtlinien konfigurieren. 
  
### <a name="add-storage-databases-to-your-topology"></a>Hinzufügen von Speicherdatenbanken zu Ihrer Topologie

Wenn Sie ihrer Topologie SQL Server Speicherdatenbanken hinzufügen, können Sie die Archivierungsdatenbanken mit einer der folgenden Optionen verbinden:
  
- Überwachungsdatenbank
    
- Back-End-Datenbank eines Enterprise Edition-Front-End-Pools
    
> [!NOTE]
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden. 
  
Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder beiden dieser Datenbanken verbinden, können Sie entweder eine einzelne SQL Instanz für eine oder alle Datenbanken verwenden oder eine separate SQL Instanz für jede Datenbank mit der folgenden Einschränkung verwenden: Jede SQL Instanz kann nur eine einzelne Back-End-Datenbank, eine einzelne Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.
  
Ausführliche Informationen zur Kollokation aller Serverrollen und Datenbanken finden Sie unter [Topologiegrundlagen für Skype for Business Server.](../../plan-your-deployment/topology-basics/topology-basics.md) Ausführliche Informationen zum Aktualisieren Ihrer Topologie, um Speicherdatenbanken einzuschließen, finden Sie unter [Erstellen und Veröffentlichen einer neuen Topologie in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>Ermitteln von Archivierungsoptionen und Benutzerrichtlinien

Sie müssen Folgendes ermitteln:
  
- Aktivieren oder Deaktivieren der Archivierung für die interne und externe Kommunikation
    
- Ob Chats, Konferenzen oder beides archiviert werden sollen
    
- Gibt an, ob der kritische Modus implementiert werden soll, der Chat- und Konferenzsitzungen bei einem Skype for Business Server Fehler blockiert. 
    
- Gibt an, ob Richtlinien für bestimmte Benutzer und Gruppen aktiviert werden sollen
    
Skype for Business Server Archivierungsoptionen können auf den folgenden Ebenen angegeben werden. 
  
- **Option auf globaler Ebene**. Dies ist die Standardarchivierungskonfiguration und gilt für die gesamte Bereitstellung. Sie wird erstellt, wenn Sie Skype for Business Server bereitstellen und standardmäßig die Archivierung für die interne und externe Kommunikation deaktivieren. Sie können diese Option nicht löschen. Wenn Sie die Löschoption auswählen, wird die globale Option auf die Standardeinstellungen zurückgesetzt.
    
- **Optionen auf Websiteebene.** Sie können die Archivierung für einen oder mehrere bestimmte Standorte aktivieren oder deaktivieren, indem Sie eine Archivierungsoption auf Standortebene für den Standort erstellen und konfigurieren. Sie können jede Archivierungsoption auf Standortebene löschen, die Sie erstellen. Eine Archivierungsoption auf Standortebene überschreibt die globale Option, jedoch nur für den in der Option angegebenen Standort. 
    
    Wenn Sie beispielsweise die Archivierung für die interne und externe Kommunikation in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung für die externe Kommunikation deaktivieren, wird nur die interne Kommunikation für diesen Standort archiviert. Wenn Sie beispielsweise die Archivierung nur für Chatnachrichten in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung sowohl für Chatnachrichten als auch für Konferenzen aktivieren, werden Konferenzen nur für den Standort archiviert, nicht für den Rest Ihrer Organisation.
    
- **Optionen auf Poolebene.** Sie können Archivierungseinstellungen für einen oder mehrere bestimmte Pools angeben, indem Sie eine Konfiguration auf Poolebene für den einzelnen Pool erstellen und konfigurieren. Eine Archivierungskonfiguration auf Poolebene ist nur vorhanden, wenn Sie sie erstellen. Sie können jede Archivierungskonfiguration auf Poolebene ändern und löschen. Eine Archivierungskonfiguration auf Poolebene setzt die globale Konfiguration und jede von Ihnen erstellte Standortarchivierungskonfiguration außer Kraft. 
    
    Angenommen, Sie aktivieren die Archivierung für Chatnachrichten nur in Ihrer globalen Konfiguration, erstellen dann eine Konfiguration auf Standortebene, in der Sie die Archivierung sowohl für Chatnachrichten als auch für Konferenzen aktivieren, und erstellen dann eine Konfiguration auf Poolebene, in der Sie die Archivierung nur für Chatnachrichten aktivieren. Die Kommunikation würde sowohl für Chatnachrichten als auch für Konferenzen für alle Benutzer des Standorts archiviert, mit Ausnahme der Benutzer, die in dem in der Konfiguration auf Poolebene angegebenen Pool verwaltet werden. Für alle anderen Benutzer in Ihrer Organisation wäre die Archivierung nur für Chatnachrichten aktiviert.
    
- **Benutzerarchivierungsrichtlinien.** Sie können die Archivierung für einen oder mehrere bestimmte Benutzer und Benutzergruppen aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie auf Benutzerebene für die angegebenen Benutzer und Benutzergruppen erstellen, konfigurieren und anwenden. Sie können jede von Ihnen erstellte Archivierungsrichtlinie auf Benutzerebene löschen und ändern, für welche Benutzer und Benutzergruppen die Archivierungsrichtlinie gilt. Eine Archivierungsrichtlinie auf Benutzerebene setzt die globale Richtlinie und alle Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, auf die die Richtlinie angewendet wird. 
    
    Angenommen, Sie deaktivieren die Archivierung für die interne und externe Kommunikation in Ihrer globalen Konfiguration, erstellen eine Richtlinie auf Standortebene, in der Sie die Archivierung für die interne und externe Kommunikation aktivieren, und erstellen dann eine Richtlinie auf Benutzerebene, in der Sie die Archivierung für die externe Kommunikation deaktivieren. Die Kommunikation würde sowohl für die externe als auch für die interne Kommunikation für alle Websitebenutzer archiviert, mit Ausnahme der Benutzer, auf die Sie die Richtlinie auf Benutzerebene anwenden. Für diese Benutzer würde nur die interne Kommunikation archiviert.
    
Ausführliche Informationen zum Einrichten anfänglicher Archivierungskonfigurationen bei der Bereitstellung der Archivierung finden Sie unter [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Ausführliche Informationen zum Verwalten der Archivierung nach der Bereitstellung finden Sie unter Verwalten der [Archivierung in Skype for Business Server.](../../manage/archiving/archiving.md) 
  
## <a name="archiving-configuration-tools"></a>Archivierungskonfigurationstools

 Sie steuern die meisten Archivierungsoptionen mithilfe der Skype for Business Server Systemsteuerung. Es stehen jedoch nur mithilfe der Skype for Business Server Verwaltungsshell einige Optionen zur Verfügung. Zu diesen Optionen gehören das Archivieren doppelter Nachrichten und das Exportieren archivierter Daten. Weitere Informationen zur Verwendung der Skype for Business Server Systemsteuerung und der Skype for Business Server-Verwaltungsshell zum Verwalten von Archivierungsrichtlinien finden Sie unter Verwalten der [Archivierung in Skype for Business Server.](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>Zugreifen auf archivierte Daten

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden: 
  
- **Microsoft Exchange Speicher.** Wenn Sie die Exchange Integrationsoption auswählen, Skype for Business Server den Archivierungsinhalt im Exchange Speicher für alle Benutzer, die in Exchange verwaltet werden, und die ihre Postfächer in In-Place Haltebereich gesetzt haben. Archivierte Daten werden in den Benutzerpostfächern des Ordners "Wiederherstellbare Elemente" gespeichert, der für Benutzer im Allgemeinen unsichtbar ist und nur von Benutzern mit einer Exchange **Discovery-Verwaltungsrolle** durchsucht werden kann. Exchange ermöglicht die Sammelsuche und -ermittlung sowie SharePoint, wenn sie bereitgestellt wird. Weitere Informationen zur Speicherung, Aufbewahrung und Ermittlung von in Exchange gespeicherten Daten finden Sie in der Dokumentation zu Exchange und SharePoint.
    
- **Skype for Business Server Archivierungsspeicher.** Wenn Sie Skype for Business Server Archivierungsdatenbanken einrichten, Skype for Business Server Archivierungsinhalte in den Skype for Business Server Archivierungsdatenbanken für alle Benutzer, die nicht in Exchange verwaltet werden, und die ihre Postfächer nicht in In-Place Archiv setzen lassen. Diese Daten sind nicht durchsuchbar, können aber in Formate exportiert werden, die mit anderen Tools durchsuchbar sind. Ausführliche Informationen zum Exportieren von in Archivierungsdatenbanken gespeicherten Daten finden Sie unter [Exportieren archivierter Daten in Skype for Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zur Archivierung finden Sie in den folgenden Themen:
  
- [Bereitstellen der Archivierung für Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Verwalten der Archivierung in Skype for Business Server](../../manage/archiving/archiving.md)
    
Weitere Informationen dazu, wie Skype for Business Server und Exchange zusammenarbeiten, finden Sie unter [Plan to integrate Skype for Business and Exchange.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
  

