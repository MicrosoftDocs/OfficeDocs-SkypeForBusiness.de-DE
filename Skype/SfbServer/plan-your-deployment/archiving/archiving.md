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
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Archivierung in Skype for Business Server planen.'
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810145"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planen der Archivierung in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Archivierung in Skype for Business Server planen.
  
Unternehmen und andere Organisationen müssen eine zunehmende Anzahl von Rechtsvorschriften beachten, die die Speicherung bestimmter Kommunikationsarten erfordern. Wenn in Ihrer Organisation solche Anforderungen erfüllt sind, können Sie die Archivierung in Skype for Business Server verwenden, um Chat- und Konferenzkommunikation (Besprechungen) zu archivieren, um einige Ihrer Complianceanforderungen zu unterstützen.
  
## <a name="archiving-components"></a>Archivierungskomponenten

Skype for Business Server verwendet die folgenden Archivierungskomponenten:
  
- **Archivierungs-Agents**. Archivierungs-Agents (auch als einheitliche Datensammlungs-Agents bezeichnet) werden auf jedem Front-End-Pool der Enterprise Edition und auf jedem Standard Edition-Server automatisch installiert und aktiviert. Archivierungs-Agents werden zwar automatisch aktiviert, nachrichten werden jedoch erst erfasst, wenn die Archivierung aktiviert und entsprechend konfiguriert ist. Standardmäßig ist die Archivierung deaktiviert.
    
- **Datenspeicher für die Archivierung**. Der Datenspeicher für Skype for Business Server kann als Skype for Business Server SQL Server-Datenbanken implementiert oder, wenn Sie über eine Exchange-Bereitstellung verfügen, in den Exchange-Speicher integriert werden. 
    
Für die Archivierung ist auch Dateispeicher erforderlich, für die Archivierung wird jedoch derselbe Dateispeicher wie für front-End-Server oder Standard Edition Server verwendet.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Bestimmen der Anforderungen Ihrer Organisation für die Archivierung

Zum Implementieren der Archivierung müssen Sie entscheiden, wie die Archivierungsanforderungen Ihrer Organisation erfüllt werden, indem Sie Folgendes bestimmen:
  
- **Welche Speicheroption verwendet werden soll.** Sie können Speicher auf eine von zwei Arten implementieren oder eine Kombination aus beiden verwenden:
    
  - **Exchange-Speicher.** Wenn Sie über eine Exchange-Bereitstellung verfügen, können Sie die Skype for Business Server- und die Exchange-Archivierung integrieren, sodass Ihre archivierten Skype for Business Server- und Exchange-Daten zusammen in Exchange gespeichert werden. Wenn Sie die Microsoft Exchange-Integrationsoption aktivieren, verwenden auf dem Exchange Server gespeicherte Benutzerpostfächer exchange-Speicher für archivierte Daten, jedoch nur, wenn die Postfächer in den In-Place wurden. Standardmäßig ist die Microsoft Exchange-Integration nicht aktiviert.
    
  - **Skype for Business Server-Speicher.** Wenn Sie Benutzer haben, die nicht in Exchange gespeichert sind oder deren Postfächer nicht im In-Place-Archiv gespeichert wurden, oder wenn Sie die Microsoft Exchange-Integration für keine oder alle Benutzer in Ihrer Bereitstellung verwenden möchten, können Sie Skype for Business Server-Archivierungsdatenbanken mithilfe von SQL Server bereitstellen.
    
- **Wann die Archivierung bereitgestellt werden soll.** Sie können die Archivierung im Rahmen Ihrer anfänglichen Skype for Business Server-Bereitstellung bereitstellen oder zu einer vorhandenen Bereitstellung hinzufügen. Verwenden Sie zum Verwenden des Skype for Business Server-Archivierungsspeichers (SQL Server-Datenbanken) den Topologie-Generator, um die Datenbanken zu Ihrer Topologie hinzuzufügen, und veröffentlichen Sie dann die Topologie erneut. Wenn alle Ihre Benutzer in Exchange gespeichert sind und ihre Postfächer im In-Place-Archiv gespeichert sind, müssen Sie Ihre Topologie nicht aktualisieren, sondern nur die Microsoft Exchange-Integration aktivieren, um archivierte Daten in Exchange zu speichern. 
    
- **Welche Standorte und Benutzer in der Organisation müssen archiviert werden?** Sie können Archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Standorte, Pools, Benutzer und Benutzergruppen konfigurieren.
    
- **Welcher Inhalt archiviert werden soll.** Unabhängig davon, ob Sie die Archivierung auf globaler Ebene oder für bestimmte Standorte und Benutzer angeben, geben Sie auf jeder dieser Ebenen an, ob die folgenden Inhaltstypen aktiviert werden sollen: 
    
  - Peer-zu-Peer-Sofortnachrichten
    
  - Konferenzen (Besprechungen), die Teil von Sofortnachrichtensitzungen mit mehreren Teilnehmern sind
    
  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)
    
  - Whiteboards und Abstimmungen für alle Teilnehmer im Rahmen einer Konferenz
    
- **Welche Inhalte können nicht archiviert werden?** Die folgenden Inhaltstypen können nicht archiviert werden: 
    
  - Peer-zu-Peer-Dateiübertragungen
    
  - Audio-/Videoinhalte für Peer-zu-Peer-Sofortnachrichten und -konferenzen
    
  - Desktop- und Anwendungsfreigaben für Peer-zu-Peer-Sofortnachrichten und -konferenzen
    
    Skype for Business Server archiviert auch keine Unterhaltungen für beständigen Chat. Zum Archivieren von Unterhaltungen für beständigen Chat müssen Sie den Kompatibilitätsdienst aktivieren und konfigurieren, bei dem es sich um eine Komponente handelt, die mit dem Server für beständigen Chat bereitgestellt werden kann. Weitere Informationen finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Weiterhin Skype for Business Server 2015 verwenden. 
    
- **Wie lange archivierte Materialien aufbewahrt werden sollen.** Die Archivierungsdatenbank ist nicht für eine langfristige Aufbewahrung vorgesehen, und Skype for Business Server bietet keine E-Discovery-Lösung (Suchlösung) für archivierte Daten, daher müssen Daten in einen anderen Speicher verschoben werden. Skype for Business Server bietet ein Sitzungsexporttool, mit dem Sie archivierte Daten exportieren und durchsuchbare Aufzeichnungen der archivierten Daten erstellen können. 
    
     Für die globale Richtlinie und für jede von Ihnen erstellten Standort- und Benutzerrichtlinie können Sie angeben, wann archivierte und exportierte Daten gelöscht werden. Weitere Informationen zum Löschen von Daten finden Sie unter "Verwalten der Bereinigung [archivierter Daten in Skype for Business Server".](../../manage/archiving/purging-of-archived-data.md) Weitere Informationen zur Verwendung des Sitzungsexporttools finden Sie unter [Exportieren archivierter Daten in Skype for Business Server.](../../manage/archiving/export-archived-data.md)
    
- **Ob die interne oder externe Kommunikation archiviert werden soll**. Sie können die Archivierung für die interne Kommunikation (die Kommunikation zwischen internen Benutzern) und/oder die externe Kommunikation (die Kommunikation, bei der mindestens ein Benutzer außerhalb Ihres internen Netzwerks beteiligt ist) aktivieren. Diese Optionen können für die gesamte Organisation oder nur für bestimmte Standorte und Pools angegeben werden. Standardmäßig ist keine dieser Optionen aktiviert.
    
    > [!NOTE]
    > Die Steuerung der Archivierung für die interne oder externe Kommunikation ist nur für Die Skype for Business-Richtlinie verfügbar. Bei der Exchange-integrierten Archivierung wird sowohl die interne als auch die externe Kommunikation archiviert. 
  
- **Gibt an, ob der kritische Modus implementiert werden soll.** Wenn die Archivierung für Ihre Organisation erforderlich ist, blockiert die Konfiguration des kritischen Modus Chat- und Konferenzsitzungen im Falle eines Skype for Business Server-Ausfalls, der die Archivierung verhindern würde. Beispiel: 
    
  - Ein Problem mit dem Skype for Business Server-Speicherdienst. In diesem Fall wird Dies für Benutzer blockiert, die für die Archivierung aktiviert sind.
    
  - Eine nicht verfügbare Dateifreigabe oder ein Problem mit dem Speicherdienst. In diesem Fall werden aktiven Konferenzen, die beim Auftreten des Fehlers im Pool gehostet werden, in den eingeschränkten Modus umgeschaltet, und neue Konferenzen können nicht aktiviert werden.
    
    Sofortnachrichten und Konferenzen werden nach dem Beheben des Fehlers automatisch wiederhergestellt.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Auswählen von Archivierungsbereitstellungs- und Konfigurationsoptionen

Die Archivierung wird bei der Bereitstellung des Servers automatisch auf jedem Front-End-Server installiert, die Archivierung wird jedoch erst aktiviert, wenn Sie sie konfigurieren. Die Konfiguration der Archivierung hängt von der Art der Bereitstellung ab. Sie können die Archivierung auf eine der folgenden Arten bereitstellen:
  
- Verwenden von Microsoft Exchange Storage
    
- Verwenden des Skype for Business Server-Speichers
    
> [!NOTE]
> Wenn Sie sowohl Skype for Business Server-Archivierungsdatenbanken implementieren als auch die Microsoft Exchange-Integration aktivieren, setzen die Exchange-Richtlinien Skype for Business Server-Archivierungsrichtlinien außer Kraft, jedoch nur für Benutzer, die in Exchange gespeichert sind und deren Postfächer in den In-Place wurden. Die Skype for Business-Archivierung hängt von der Microsoft Exchange-In-Place A0 ab. 
  
Wenn Sie die Archivierung für einen Front-End-Pool oder Standard Edition-Server bereitstellen, sollten Sie sie für alle anderen Front-End-Pools und Standard Edition-Server in Ihrer Bereitstellung aktivieren. Wenn die Archivierung für den Pool, in dem eine Unterhaltung oder Besprechung gehostet wird, nicht aktiviert ist, werden möglicherweise nicht alle Konferenzdaten archiviert. Die Archivierung funktioniert weiterhin für Imnachrichten, konferenzinhalte und -ereignisse werden jedoch möglicherweise nicht archiviert.
  
> [!NOTE]
> Um die Delegierung von Verwaltungsaufgaben zu ermöglichen und gleichzeitig die Sicherheitsstandards Ihrer Organisation zu erhalten, verwendet Skype for Business Server die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC). Mit rbAC werden Administratorrechte gewährt, indem Benutzer vordefinierten Administratorrollen zugewiesen werden. Zum Konfigurieren von Skype for Business-Archivierungsrichtlinien und -konfigurationen muss dem Benutzer die Rolle "CsArchivingAdministrator" zugewiesen werden (es sei denn, die Konfiguration erfolgt direkt auf dem Server, auf dem die Archivierung bereitgestellt wird, anstatt remote von einem anderen Computer aus). Eine Liste der Benutzerrechte, -berechtigungen und -rollen, die für die Archivierungsbereitstellung erforderlich sind, finden Sie unter "Bereitstellen der [Archivierung für Skype for Business Server".](../../deploy/deploy-archiving/deploy-archiving.md) 
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration verwenden, sind für die Konfiguration von Exchange-Richtlinien entsprechende Administratorrechte und -berechtigungen erforderlich. Ausführliche Informationen finden Sie in der Exchange-Dokumentation. 
  
### <a name="microsoft-exchange-storage"></a>Microsoft Exchange Storage

 Wenn Sie die Microsoft Exchange-Integration auswählen, verwenden Sie die Exchange-Richtlinien und -Konfigurationen, um die Archivierung von Skype for Business Server zu steuern. Sie können die Microsoft Exchange-Integrationsoption auf globaler, Standort- und Poolebene konfigurieren. Wenn Ihre Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Einstellungen zwischen Skype for Business Server und Exchange synchronisieren. Sie müssen dies bestimmen:
  
- Ob Im-, Konferenz- oder beides archiviert werden soll
    
- Ob der kritische Modus implementiert werden soll, der Chat- und Konferenzsitzungen bei einem Ausfall von Skype for Business Server blockiert 
    
- Auswahl der Microsoft Exchange-Integrationsoption für die Verwendung von Exchange zum Speichern archivierter Daten
    
Informationen zum Konfigurieren von Exchange In-Place-Archivrichtlinien und -einstellungen zur Unterstützung der Archivierung finden Sie in der Exchange-Produktdokumentation.
  
### <a name="skype-for-business-server-storage"></a>Skype for Business Server-Speicher

Wenn Sie den Skype for Business Server-Speicher auswählen, verwenden Sie Skype for Business Server-Archivierungsrichtlinien und -konfigurationen, um zu steuern, wie die Archivierung aktiviert und implementiert wird. Skype for Business Server storage uses SQL Server databases, so you will need to add the appropriate SQL Server databases to your topology, then configure your archiving policies. 
  
### <a name="add-storage-databases-to-your-topology"></a>Hinzufügen von Speicherdatenbanken zur Topologie

Beim Hinzufügen SQL Server speicherdatenbanken zu Ihrer Topologie können Sie die Archivierungsdatenbanken mit einer der folgenden Optionen zusammengef?nnen:
  
- Überwachungsdatenbank
    
- Back-End-Datenbank eines Enterprise Edition-Front-End-Pools
    
> [!NOTE]
> Auf dem Server, auf dem die Archivierungsdatenbank gehostet wird, können auch andere Datenbanken gehostet werden. Wenn Sie die Archivierungsdatenbank mit anderen Datenbanken verbinden, kann die Archivierungsdatenbank bei Archivierung der Nachrichten vieler Benutzer sehr viel Speicherplatz auf dem Datenträger belegen. Aus diesem Grund wird nicht empfohlen, die Archivierungsdatenbank mit der Back-End-Datenbank zu verbinden. 
  
Wenn Sie die Archivierungsdatenbank mit der Überwachungsdatenbank, der Back-End-Datenbank oder beiden dieser Datenbanken gleichzeitig verwenden, können Sie entweder eine einzelne SQL-Instanz für eine oder alle Datenbanken oder eine separate SQL-Instanz für jede Datenbank mit der folgenden Einschränkung verwenden: Jede SQL-Instanz kann nur eine einzelne Back-End-Datenbank, eine einzelne Überwachungsdatenbank und eine einzelne Archivierungsdatenbank enthalten.
  
Weitere Informationen zum Verbinden aller Serverrollen und Datenbanken finden Sie unter [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Weitere Informationen zum Aktualisieren Ihrer Topologie mit Speicherdatenbanken finden Sie unter Erstellen und Veröffentlichen einer neuen [Topologie in Skype for Business Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>Festlegen von Archivierungsoptionen und Benutzerrichtlinien

Sie müssen dies bestimmen:
  
- Aktivieren oder Deaktivieren der Archivierung für die interne und externe Kommunikation
    
- Ob Im-, Konferenz- oder beides archiviert werden soll
    
- Ob der kritische Modus implementiert werden soll, der Chat- und Konferenzsitzungen bei einem Ausfall von Skype for Business Server blockiert 
    
- Gibt an, ob Richtlinien für bestimmte Benutzer und Gruppen aktiviert werden sollen
    
Die Archivierungsoptionen für Skype for Business Server können auf den folgenden Ebenen angegeben werden. 
  
- **Option auf globaler Ebene**. Dies ist die Standardarchivierungskonfiguration und gilt für die gesamte Bereitstellung. Sie wird bei der Bereitstellung von Skype for Business Server erstellt und deaktiviert standardmäßig die Archivierung für die interne und die externe Kommunikation. Diese Option kann nicht gelöscht werden. Wenn Sie die Option zum Löschen auswählen, wird die globale Option auf die Standardeinstellungen zurückgesetzt.
    
- **Optionen auf Websiteebene.** Sie können die Archivierung für einen oder mehrere bestimmte Standorte aktivieren oder deaktivieren, indem Sie eine Archivierungsoption auf Standortebene für den Standort erstellen und konfigurieren. Sie können jede Archivierungsoption auf Standortebene löschen, die Sie erstellen. Eine Archivierungsoption auf Standortebene setzt die globale Option außer Kraft, jedoch nur für den in der Option angegebenen Standort. 
    
    Wenn Sie beispielsweise die Archivierung für die interne und externe Kommunikation in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung für die externe Kommunikation deaktivieren, wird nur die interne Kommunikation für diesen Standort archiviert. Ein weiteres Beispiel: Wenn Sie die Archivierung nur für Denkdaten in Ihrer globalen Konfiguration aktivieren und eine Standortkonfiguration erstellen, in der Sie die Archivierung sowohl für Dies als auch für Konferenzen aktivieren, werden Die Konferenzen nur für den Standort und nicht für den Rest Der Organisation archiviert.
    
- **Optionen auf Poolebene.** Sie können Archivierungseinstellungen für einen oder mehrere bestimmte Pools angeben, indem Sie eine Konfiguration auf Poolebene für den einzelnen Pool erstellen und konfigurieren. Eine Archivierungskonfiguration auf Poolebene ist nur vorhanden, wenn Sie sie erstellen. Sie können jede Archivierungskonfiguration auf Poolebene ändern und löschen. Eine Archivierungskonfiguration auf Poolebene setzt die globale Konfiguration und die von Ihnen möglicherweise erstellte Standortarchivierungskonfiguration außer Kraft. 
    
    Angenommen, Sie aktivieren die Archivierung für Denkdaten nur in Ihrer globalen Konfiguration, erstellen dann eine Konfiguration auf Standortebene, in der Sie die Archivierung sowohl für Im- als auch für Konferenzen aktivieren, und erstellen dann eine Konfiguration auf Poolebene, in der Sie die Archivierung nur für Dies aktivieren. Die Kommunikation würde sowohl für Dies als auch für Konferenzen für alle Benutzer des Standorts archiviert, mit Ausnahme der Benutzer, die in dem in der Konfiguration auf Poolebene angegebenen Pool gespeichert sind. Für alle anderen Benutzer in Ihrer Organisation würde die Archivierung nur für Dies aktiviert.
    
- **Benutzerarchivierungsrichtlinien**. Sie können die Archivierung für einen oder mehrere bestimmte Benutzer und Benutzergruppen aktivieren oder deaktivieren, indem Sie eine Archivierungsrichtlinie auf Benutzerebene für die angegebenen Benutzer und Benutzergruppen erstellen, konfigurieren und anwenden. Sie können jede archivierungsrichtlinie auf Benutzerebene löschen, die Sie erstellen, und Sie können ändern, für welche Benutzer und Benutzergruppen die Archivierungsrichtlinie gilt. Eine Archivierungsrichtlinie auf Benutzerebene setzt die globale Richtlinie und alle Standortrichtlinien außer Kraft, jedoch nur für die Benutzer und Benutzergruppen, auf die die Richtlinie angewendet wird. 
    
    Angenommen, Sie deaktivieren die Archivierung für die interne und externe Kommunikation in Ihrer globalen Konfiguration, erstellen eine Richtlinie auf Standortebene, in der Sie die Archivierung für die interne und externe Kommunikation aktivieren, und erstellen dann eine Richtlinie auf Benutzerebene, in der Sie die Archivierung für die externe Kommunikation deaktivieren. Die Kommunikation würde sowohl für die externe als auch für die interne Kommunikation für alle Websitebenutzer archiviert, mit Ausnahme der Benutzer, auf die Sie die Richtlinie auf Benutzerebene anwenden– für diese Benutzer würde nur die interne Kommunikation archiviert.
    
Weitere Informationen zum Einrichten der anfänglichen Archivierungskonfigurationen bei der Bereitstellung der Archivierung finden Sie unter "Bereitstellen der [Archivierung für Skype for Business Server".](../../deploy/deploy-archiving/deploy-archiving.md) Weitere Informationen zum Verwalten der Archivierung nach der Bereitstellung finden Sie unter ["Verwalten der Archivierung in Skype for Business Server".](../../manage/archiving/archiving.md) 
  
## <a name="archiving-configuration-tools"></a>Archivierungskonfigurationstools

 Sie steuern die meisten Archivierungsoptionen mithilfe der Skype for Business Server-Systemsteuerung. Es gibt jedoch einige Optionen, die nur über die Skype for Business Server-Verwaltungsshell verfügbar sind. Zu diesen Optionen gehören das Archivieren doppelter Nachrichten und das Exportieren archivierter Daten. Weitere Informationen zur Verwendung der Skype for Business Server-Systemsteuerung und der Skype for Business Server-Verwaltungsshell zum Verwalten von Archivierungsrichtlinien finden Sie unter "Verwalten der Archivierung [in Skype for Business Server".](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>Zugreifen auf archivierte Daten

Der Zugriff auf archivierte Daten ist abhängig davon, wo die Daten gespeichert wurden: 
  
- **Microsoft Exchange-Speicher**. Wenn Sie die Option für die Integration von Exchange auswählen, werden die Archivierungsinhalte von Skype for Business Server im Exchange Store für alle Benutzer gespeichert, die in Exchange gespeichert sind und deren Postfächer in den In-Place wurden. Archivierte Daten werden im Ordner "Wiederherstellbare Elemente" des Benutzerpostfachs gespeichert, der für Benutzer in der Regel nicht sichtbar ist und nur von Benutzern mit einer Rolle "Exchange **Discovery Management" durchsucht werden** kann. Exchange ermöglicht die Sammelsuche und -ermittlung zusammen mit SharePoint, wenn es bereitgestellt wird. Weitere Informationen zur Speicherung, Aufbewahrung und Ermittlung von in Exchange gespeicherten Daten finden Sie in der Exchange- und SharePoint-Dokumentation.
    
- **Skype for Business Server-Archivierungsspeicher**. Wenn Sie Skype for Business Server-Archivierungsdatenbanken einrichten, überlagert Skype for Business Server Archivierungsinhalte in den Skype for Business Server-Archivierungsdatenbanken für alle Benutzer, die nicht in Exchange gespeichert sind und deren Postfächer nicht im Archiv In-Place waren. Diese Daten sind nicht durchsuchbar, können jedoch in Formate exportiert werden, die mit anderen Tools durchsuchbar sind. Weitere Informationen zum Exportieren von in Archivierungsdatenbanken gespeicherten Daten finden Sie unter ["Exportieren archivierter Daten in Skype for Business Server".](../../manage/archiving/export-archived-data.md)
    
## <a name="for-more-information"></a>Weitere Informationen

Weitere Informationen zur Archivierung finden Sie in den folgenden Themen:
  
- [Bereitstellen der Archivierung für Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Verwalten der Archivierung in Skype for Business Server](../../manage/archiving/archiving.md)
    
Weitere Informationen zur Zusammenarbeit von Skype for Business Server und Exchange finden Sie unter "Planen der Integration von [Skype for Business und Exchange".](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
  

