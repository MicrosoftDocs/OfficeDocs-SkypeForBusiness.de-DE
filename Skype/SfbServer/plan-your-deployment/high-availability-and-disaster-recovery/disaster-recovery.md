---
title: Notfallwiederherstellung des Front-End-Pools in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Für die Notfallwiederherstellung bietet Skype for Business Server die Poolkopplung mit einem Failover, falls ein Pool ausfallen sollte.
ms.openlocfilehash: 949b0c51ba3ad545210f70c311f8db1912623291
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093133"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Notfallwiederherstellung des Front-End-Pools in Skype for Business Server
 
Für die Notfallwiederherstellung bietet Skype for Business Server die Poolkopplung mit einem Failover, falls ein Pool ausfallen sollte.
  
Stellen Sie für die robustesten Notfallwiederherstellungsoptionen in Skype for Business Server Front-End-Pools auf zwei geografisch verteilten Standorten zur Verfügung. Jeder Standort verfügt über einen Front-End-Pool, der mit einem entsprechenden Front-End-Pool am anderen Standort gekoppelt ist. Beide Standorte sind aktiv, und der Sicherungsdienst bietet eine Echtzeitdatenreplikation, um die Pools synchron zu halten. Weitere Informationen finden Sie unter Bereitstellen von gekoppelten [Front-End-Pools](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) für die Notfallwiederherstellung in Skype for Business Server, wenn Sie die Front-End-Poolkopplung implementieren möchten.
  
![Zeigt Front-End-Pools an zwei verschiedenen Standorten an, die miteinander gekoppelt sind](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Wenn für den Pool an einem Standort ein Fehler auftritt, können Sie die Benutzer aus diesem Pool in den Pool am anderen Standort übergehen, der dann alle Benutzer in beiden Pools bedient. Für die Kapazitätsplanung sollten Sie jeden Pool so entwerfen, dass er die Arbeitslast aller Benutzer in beiden Pools im Notfall verarbeiten kann.
  
Zwei Rechenzentren, die Front-End-Pools enthalten, die miteinander gekoppelt sind, können einen beliebigen Abstand voneinander haben. Es wird empfohlen, zwei Rechenzentren in derselben Weltregion mit schnellen Verbindungen zwischen diesen zu koppeln. 
  
Es ist möglich, zwei Rechenzentren in allen Regionen der Welt zu haben, aber bei einem Notfall kann aufgrund der Latenz bei der Datenreplikation ein höherer Datenverlust auftreten.
  
Wenn Sie planen, welche Pools gekoppelt werden sollen, müssen Sie beachten, dass nur die folgenden Kopplungen unterstützt werden:
  
- Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.
    
- Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.
    
- Pools, die miteinander gekoppelt sind, müssen dasselbe Basisbetriebssystem ausführen.
    
Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Kopplungstypen werden jedoch nicht unterstützt.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Beziehungen zwischen Sicherungsregistrierungsstellen und Survivable Branch Appliances

Zusätzlich zur Bereitstellung der Notfallwiederherstellungs-Fähigkeit dienen zwei gekoppelte Pools als Sicherungsregistrierungsstellen füreinander. Jeder Pool kann die Sicherung nur für einen anderen Front-End-Pool sein.
  
Obwohl Sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool weiterhin die Sicherungsregistrierungsstelle für eine beliebige Anzahl von Survivable Branch Appliances sein.
  
Beachten Sie, dass Skype for Business die Notfallwiederherstellungsunterstützung nicht auf Benutzer aus einer Survivable Branch Appliance erweitert. Wenn ein Front-End-Pool, der als Sicherung für eine Survivable Branch Appliance dient, ausbleicht, wechseln Benutzer, die bei der Survivable Branch Appliance angemeldet sind, in den Ausfallsicherheitsmodus, obwohl benutzer, die im Front-End-Pool gespeichert sind, einen Fehler im Front-End-Sicherungspool haben.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Wiederherstellungszeit für Poolfailover und Pool-Failback

Bei Poolfailover und Pool-Failback beträgt das Engineeringziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 15 bis 20 Minuten. Dies ist die Zeit, die für das Failover erforderlich ist, nachdem Administratoren festgestellt haben, dass ein Notfall vor sich ging und die Failoverprozeduren gestartet wurden. Es enthält weder die Zeit für Administratoren, die Situation zu bewerten und eine Entscheidung zu treffen, noch die Zeit, in der sich Benutzer nach Abschluss des Failovers erneut anmelden können.
  
Bei Poolfailover und Pool-Failback beträgt das Engineeringziel für das Wiederherstellungspunktziel (Recovery Point Objective, RPO) 5 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können. Wenn beispielsweise ein Pool um 10:00 Uhr abgeht und das RPO 5 Minuten beträgt, werden daten zwischen 9:55 Uhr in den Pool geschrieben. und 10:00 Uhr wurde möglicherweise nicht in den Sicherungspool repliziert und würde verloren gehen.
  
Bei allen RTO- und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren in derselben Weltregion befinden, und dass sich der Transport mit hoher Geschwindigkeit und geringer Latenz zwischen den beiden Standorten befindet. Diese Zahlen werden für einen Pool mit 40.000 gleichzeitig aktiven Benutzern und 200.000 Benutzern gemessen, die für Skype for Business aktiviert sind, was ein vordefiniertes Benutzermodell mit keinem Rückstau bei der Datenreplikation anbeutet. Sie können sich basierend auf Leistungstests und -überprüfungen ändern.
  
## <a name="central-management-store-failover"></a>Failover des zentralen Verwaltungsspeichers

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu den Servern und Diensten in Ihrer Bereitstellung. Jede Skype for Business Server-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pools gehostet wird.
  
Wenn Sie den Pool koppeln, der den zentralen Verwaltungsspeicher hostet, wird im Sicherungspool eine Zentrale Speicherdatenbank für die Sicherung eingerichtet. An einem beliebigen Punkt ist eine der beiden zentralen Verwaltungsspeicherdatenbanken aktiv, und die andere ist standby. Der Inhalt wird vom Sicherungsdienst aus der aktiven Datenbank in den Standbymodus repliziert.
  
![Zeigt zwei Front-End-Pools an, einen mit dem aktiven CMS-Speicher und den anderen mit dem passiven CMS-Sicherungsspeicher](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Während eines Poolfailovers, das den Pool umfasst, der den zentralen Verwaltungsspeicher hosten soll, müssen Sie einen Fehler über den zentralen Verwaltungsspeicher ausführen, bevor Sie einen Fehler über den Front-End-Pool ausführen.
  
Nach der Reparatur des Notfalls ist es nicht erforderlich, den zentralen Verwaltungsspeicher zurück zu führen. Der zentrale Verwaltungsspeicher kann in dem Pool verbleiben, in den er nicht überfehlt wurde.
  
Die technischen Ziele für das Failover des zentralen Verwaltungsspeichers sind 5 Minuten für das Ziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) und 5 Minuten für das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Front-End-Pool-Kopplungsdatensicherheit

Der Sicherungsdienst überträgt Benutzerdaten und Konferenzinhalte kontinuierlich zwischen zwei gekoppelten Front-End-Pools. Die Benutzerdaten enthalten BENUTZER-SIP-URIs sowie Konferenzzeitpläne, Kontaktlisten und Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint-Uploads sowie Whiteboards, die in Konferenzen verwendet werden.
  
Aus dem Quellpool werden diese Daten aus dem lokalen Speicher exportiert, gezippt und dann in den Zielpool übertragen, wo sie entzippt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass sich die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks befindet, das vor dem Internet geschützt ist. Die übertragenen Daten zwischen den beiden Rechenzentren werden nicht verschlüsselt, und die Daten werden auch nicht systemeigene in einem sicheren Protokoll, z. B. HTTPS, gekapselt. Daher ist ein Man-in-the-Middle-Angriff von internem Personal innerhalb des Unternehmensnetzwerks möglich.
  
Jedes Unternehmen, das Skype for Business Server über mehrere Rechenzentren hinweg bereitgestellt und das Notfallwiederherstellungsfeature verwendet, muss sicherstellen, dass der Datenverkehr zwischen Rechenzentren durch das Unternehmensintranet geschützt ist. Unternehmen, die sich um den internen Angriffsschutz kümmern, müssen die Kommunikationsverbindungen zwischen den Rechenzentren sichern. Dies ist eine Standardanforderung, die auch viele andere Arten vertraulicher Unternehmensdaten unterstützt, die zwischen Rechenzentren übertragen werden.
  
Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die vom Sicherungsdienst verfügbar gemachten Benutzerdaten (z. B. SIP-URIs) stehen im Allgemeinen allen Mitarbeitern im Unternehmen über andere Mittel wie das globale Adressbuch oder andere Verzeichnissoftware zur Verfügung. Daher sollte der Fokus auf der Sicherung des WAN zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen den beiden gekoppelten Pools verwendet wird.
  
### <a name="mitigating-security-risks"></a>Minderung von Sicherheitsrisiken

Sie haben viele Möglichkeiten, den Sicherheitsschutz für den Sicherungsdienstdatenverkehr zu verbessern. Dies reicht von der Einschränkung des Zugriffs auf die Rechenzentren bis zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die Skype for Business Server bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die nach Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für den Aufbau einer sicheren IT-Infrastruktur. Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) . 
  
Wir implizieren nicht, dass sie die einzige Lösung ist, noch implizieren wir, dass sie die bevorzugte Lösung für Skype for Business Server ist. Es wird empfohlen, dass Unternehmenskunden die Lösung basierend auf ihrer IT-Sicherheitsinfrastruktur und ihren Anforderungen für ihre spezifischen Anforderungen auswählen. In der Beispiellösung von Microsoft werden IPSec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet.
  
Eine weitere mögliche Lösung besteht in der Verwendung von IPSec, um die vom Sicherungsdienst selbst gesendeten Daten zu schützen. Wenn Sie diese Methode auswählen, sollten Sie die IPSec-Regeln für das SMB-Protokoll für die folgenden Server konfigurieren, wobei Pool A und Pool B zwei gekoppelte Front-End-Pools sind.
  
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A bis zum Dateispeicher, der von Pool B verwendet wird.
    
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B bis zum Dateispeicher, der von Pool A verwendet wird.
    
> [!CAUTION]
>  IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene vorgesehen, z. B. SSL/TLS. Ein Vorteil der Verwendung von IPsec besteht in der Bereitstellung von Netzwerkdatenverkehrsicherheit für vorhandene Anwendungen, ohne sie ändern zu müssen. Unternehmen, die nur den Transport zwischen den beiden Rechenzentren sichern möchten, sollten ihre jeweiligen Netzwerkhardwareanbieter über Möglichkeiten zum Einrichten sicherer WAN-Verbindungen mithilfe der Geräte des Anbieters informieren.
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen von gekoppelten Front-End-Pools für die Notfallwiederherstellung in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)