---
title: Notfallwiederherstellung für Front-End-Pools in Skype for Business Server
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
description: Für die Notfallwiederherstellung bietet Skype for Business Server die Poolpaarung mit einem Failover für den Fall, dass ein Pool ausfallt.
ms.openlocfilehash: d77a0d56c7a3e3d80c6e735fd6eff178606f667a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802915"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Notfallwiederherstellung für Front-End-Pools in Skype for Business Server
 
Für die Notfallwiederherstellung bietet Skype for Business Server die Poolpaarung mit einem Failover für den Fall, dass ein Pool ausfallt.
  
Für die robustesten Notfallwiederherstellungsoptionen in Skype for Business Server stellen Sie Front-End-Poolspaare an zwei geografisch verteilten Standorten zur Verfügung. Jeder Standort verfügt über einen Front-End-Pool, der mit einem entsprechenden Front-End-Pool am anderen Standort gekoppelt ist. Beide Standorte sind aktiv, und der Sicherungsdienst bietet eine Datenreplikation in Echtzeit, um die Pools synchron zu halten. Informationen [zum Bereitstellen von Front-End-Poolpaaren](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) für die Notfallwiederherstellung in Skype for Business Server finden Sie, wenn Sie die Front-End-Poolpaarung implementieren möchten.
  
![Zeigt Front-End-Pools an zwei unterschiedlichen Standorten, die miteinander gekoppelt sind](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Wenn der Pool an einem Standort ausfällt, können Sie ein Failover der Benutzer von diesem Pool zum Pool am anderen Standort, der dann alle Benutzer in beiden Pools bedient. Für die Kapazitätsplanung sollten Sie jeden Pool so entwerfen, dass er die Arbeitslast aller Benutzer in beiden Pools im Notfall bewältigen kann.
  
Zwei Rechenzentren mit front-End-Pools, die miteinander gekoppelt sind, können einen beliebigen Abstand voneinander haben. Es wird empfohlen, zwei Rechenzentren in derselben Weltregion mit Hochgeschwindigkeitsverbindungen zu koppeln. 
  
Es ist möglich, zwei Rechenzentren in allen Weltregionen zu haben, kann jedoch aufgrund der Latenz bei der Datenreplikation zu einem höheren Datenverlust führen, wenn es zu einem Notfall kommt.
  
Wenn Sie planen, welche Pools gekoppelt werden sollen, müssen Sie berücksichtigen, dass nur die folgenden Paarungen unterstützt werden:
  
- Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.
    
- Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.
    
- Pools, die gekoppelt sind, müssen das gleiche Basisbetriebssystem ausführen.
    
Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Paarungstypen werden jedoch nicht unterstützt.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Sicherungsregistrierungsbeziehungen und Survivable Branch Appliances

Neben der Notfallwiederherstellung dienen zwei paarte Pools als Sicherungsregistrierungsstellen füreinander. Jeder Pool kann die Sicherung nur für einen anderen Front-End-Pool sein.
  
Auch wenn sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool dennoch auch die Sicherungsregistrierung für eine beliebige Anzahl von Survivable Branch Appliances sein.
  
Beachten Sie, dass Skype for Business die Unterstützung für die Notfallwiederherstellung nicht auf Benutzer aus einer Survivable Branch Appliance ausd verlängert. Wenn ein Front-End-Pool, der als Sicherung für eine Survivable Branch Appliance dient, ausbleief, wechseln Benutzer, die bei der Survivable Branch Appliance angemeldet sind, in den Ausfallsicherheitsmodus, obwohl benutzer, die im Front-End-Pool gespeichert sind, auf den Front-End-Sicherungspool umgeschaltet werden.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Wiederherstellungszeit für Poolfailover und Poolf failback

Bei Poolfailover und Poolf failback beträgt das Entwicklungsziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 15 bis 20 Minuten. Dies ist die Zeit, die für das Failover erforderlich ist, nachdem Administratoren festgestellt haben, dass es zu einem Notfall gekommen ist, und die Failoverprozeduren gestartet haben. Es umfasst weder die Zeit, die Administratoren zum Bewerten der Situation und zum Treffen einer Entscheidung haben, noch die Zeit, die Benutzer sich nach Abschluss des Failovers erneut anmelden müssen.
  
Bei Poolfailover und Poolf failback beträgt das Engineeringziel für den Wiederherstellungspunkt (Recovery Point Objective, RPO) 5 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können. Wenn beispielsweise ein Pool um 10:00 Uhr ausgeht und das RPO 5 Minuten beträgt, werden daten zwischen 9:55 Uhr in den Pool geschrieben. und 10:00 Uhr wurden möglicherweise nicht in den Sicherungspool repliziert und gehen verloren.
  
Bei allen RTO- und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren in derselben Weltregion befinden, und dass sich der Transport mit hoher Geschwindigkeit und geringer Latenz zwischen den beiden Standorten befindet. Diese Zahlen werden für einen Pool mit 40.000 gleichzeitig aktiven Benutzern und 200.000 für Skype for Business aktivierten Benutzern im Hinblick auf ein vordefiniertes Benutzermodell gemessen, bei dem bei der Datenreplikation kein Rückstau besteht. Sie können sich basierend auf Leistungstests und Überprüfungen ändern.
  
## <a name="central-management-store-failover"></a>Failover des zentralen Verwaltungsspeichers

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu den Servern und Diensten in Ihrer Bereitstellung. Jede Skype for Business Server-Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pools gehostet wird.
  
Wenn Sie den Pool koppeln, der den zentralen Verwaltungsspeicher hostet, wird im Sicherungspool eine Datenbank des zentralen Sicherungsspeichers eingerichtet. Zu jedem Zeitpunkt ist eine der beiden zentralen Verwaltungsspeicherdatenbanken aktiv, die andere ist standby. Der Inhalt wird vom Sicherungsdienst aus der aktiven Datenbank in den Standbymodus repliziert.
  
![Zeigt zwei Front-End-Pools an, einen mit dem aktiven UND den anderen mit dem passiven Sicherungs-CMS-Speicher.](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Während eines Poolfailovers, an dem der Pool mit dem zentralen Verwaltungsspeicher ausgeführt wird, müssen Sie ein Failover des zentralen Verwaltungsspeichers ausführen, bevor Sie ein Failover für den Front-End-Pool ausführen.
  
Nach der Reparatur des Notfalls muss kein Fail back für den zentralen Verwaltungsspeicher mehr erforderlich sein. Der zentrale Verwaltungsspeicher kann in dem Pool verbleiben, für den sie einen Fehler auftrat.
  
Die Technischen Ziele für das Failover des zentralen Verwaltungsspeichers sind 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) und 5 Minuten für das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Datensicherheit für die Front-End-Poolpaarung

Der Sicherungsdienst überträgt kontinuierlich Benutzerdaten und Konferenzinhalte zwischen zwei gekoppelten Front-End-Pools. Die Benutzerdaten enthalten BENUTZER-SIP-URIs sowie Konferenzzeitpläne, Kontaktlisten und Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint-Uploads sowie Whiteboards, die in Konferenzen verwendet werden.
  
Aus dem Quellpool werden diese Daten aus dem lokalen Speicher exportiert, gezippt und dann in den Zielpool übertragen, wo sie entzippt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass sich die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks befindet, das vor dem Internet geschützt ist. Die übertragenen Daten zwischen den beiden Rechenzentren werden nicht verschlüsselt, und die Daten sind auch nicht systemintehativ in einem sicheren Protokoll wie HTTPS gekapselt. Daher ist ein Man-in-the-Middle-Angriff von internen Mitarbeitern innerhalb des Unternehmensnetzwerks möglich.
  
Jedes Unternehmen, das Skype for Business Server über mehrere Rechenzentren hinweg bereitstellen und die Notfallwiederherstellungsfunktion verwendet, muss sicherstellen, dass der Datenverkehr zwischen Rechenzentren durch das Unternehmensintranet geschützt wird. Unternehmen, die sich um internen Angriffsschutz kümmern, müssen die Kommunikationsverbindungen zwischen den Rechenzentren sichern. Dies ist eine Standardanforderung, die auch viele andere Typen vertraulicher Unternehmensdaten unterstützt, die zwischen Rechenzentren übertragen werden.
  
Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere die vom Sicherungsdienst verfügbar gemachten Benutzerdaten (z. B. SIP-URIs) sind im Allgemeinen für alle Mitarbeiter im Unternehmen über andere Mittel verfügbar, z. B. das globale Adressbuch oder andere Verzeichnissoftware. Daher sollte der Schwerpunkt auf der Sicherung des WAN zwischen den beiden Rechenzentren liegen, wenn der Sicherungsdienst zum Kopieren von Daten zwischen den beiden Paarpools verwendet wird.
  
### <a name="mitigating-security-risks"></a>Minderung von Sicherheitsrisiken

Es gibt viele Möglichkeiten, den Sicherheitsschutz für den Sicherungsdienstdatenverkehr zu verbessern. Dies reicht von der Einschränkung des Zugriffs auf die Rechenzentren bis zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die Skype for Business Server bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur. Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544) . 
  
Wir implizieren nicht, dass es sich um die einzige Lösung handelt, noch implizieren wir, dass sie die bevorzugte Lösung für Skype for Business Server ist. Es wird empfohlen, dass Unternehmenskunden die Lösung auswählen, die ihren spezifischen Anforderungen entspricht, basierend auf ihrer It-Security-Infrastruktur und ihren Anforderungen. In der Beispiellösung von Microsoft werden IPSec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet.
  
Eine weitere mögliche Lösung besteht in der Verwendung von IPSec, um die vom Sicherungsdienst selbst gesendeten Daten zu schützen. Wenn Sie diese Methode auswählen, sollten Sie die IPSec-Regeln für das SMB-Protokoll für die folgenden Server konfigurieren, wobei Pool A und Pool B zwei gepaarte Front-End-Pools sind.
  
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A zum von Pool B verwendeten Dateispeicher.
    
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B zum von Pool A verwendeten Dateispeicher.
    
> [!CAUTION]
>  IPsec ist nicht als Ersatz für Sicherheit auf Anwendungsebene vorgesehen, z. B. SSL/TLS. Ein Vorteil der Verwendung von IPsec besteht in der Bereitstellung von Netzwerkdatenverkehrsicherheit für vorhandene Anwendungen, ohne sie ändern zu müssen. Unternehmen, die nur den Transport zwischen den beiden Rechenzentren sichern möchten, sollten sich an die jeweiligen Netzwerkhardwareanbieter wenden, um Möglichkeiten zum Einrichten sicherer WAN-Verbindungen mithilfe der Geräte des Anbieters zu erhalten.
  
## <a name="see-also"></a>Weitere Informationen

[Bereitstellen gepaarter Front-End-Pools für die Notfallwiederherstellung in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
