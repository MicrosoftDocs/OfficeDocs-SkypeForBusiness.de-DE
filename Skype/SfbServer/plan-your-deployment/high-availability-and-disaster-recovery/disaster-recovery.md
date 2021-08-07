---
title: Notfallwiederherstellung von Front-End-Pools in Skype for Business Server
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
description: Für die Notfallwiederherstellung bietet Skype for Business Server eine Poolpaarung mit Failover für den Fall, dass ein Pool ausfällt.
ms.openlocfilehash: a7e658e10718ac45ee6c2122433137ac4a198a459baa0171aec2453963636d32
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276626"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Notfallwiederherstellung von Front-End-Pools in Skype for Business Server
 
Für die Notfallwiederherstellung bietet Skype for Business Server eine Poolpaarung mit Failover für den Fall, dass ein Pool ausfällt.
  
Stellen Sie für die stabilsten Notfallwiederherstellungsoptionen in Skype for Business Server Front-End-Pools an zwei geografisch verteilten Standorten bereit. Jeder Standort verfügt über einen Front-End-Pool, der mit einem entsprechenden Front-End-Pool am anderen Standort gekoppelt ist. Beide Standorte sind aktiv, und der Sicherungsdienst bietet eine Echtzeitdatenreplikation, um die Pools synchronisiert zu halten. Informationen zur Notfallwiederherstellung in Skype for Business Server, wenn Sie die Front-End-Poolpaarung implementieren möchten, finden Sie unter "Bereitstellen von [front-End-Poolpaaren".](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
  
![Zeigt Front-End-Pools an zwei verschiedenen Standorten an, die miteinander gekoppelt sind](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Wenn der Pool an einem Standort fehlschlägt, können Sie einen Failover der Benutzer aus diesem Pool auf den Pool am anderen Standort ausführen, der dann alle Benutzer in beiden Pools bedient. Für die Kapazitätsplanung sollten Sie jeden Pool so entwerfen, dass er die Arbeitsauslastung aller Benutzer in beiden Pools im Notfall verarbeiten kann.
  
Zwei Rechenzentren, die miteinander gekoppelte Front-End-Pools enthalten, können beliebig weit voneinander entfernt sein. Es wird empfohlen, zwei Rechenzentren in derselben Weltregion mit hochschnellen Verbindungen zu koppeln. 
  
Es ist möglich, zwei Rechenzentren auf der ganzen Welt zu haben, kann aber aufgrund der Latenz bei der Datenreplikation zu einem höheren Datenverlust führen, wenn ein Notfall auftritt.
  
Wenn Sie planen, welche Pools gekoppelt werden sollen, müssen Sie bedenken, dass nur die folgenden Kopplungen unterstützt werden:
  
- Enterprise Edition-Pools können nur mit anderen Enterprise Edition-Pools gepaart werden. Entsprechend können Standard Edition-Pools nur mit anderen Standard Edition-Pools gepaart werden.
    
- Physische Pool können nur mit andere physischen Pools gepaart werden. Entsprechend können virtuelle Pools nur mit anderen virtuellen Pools gepaart werden.
    
- Pools, die miteinander gekoppelt sind, müssen dasselbe Basisbetriebssystem ausführen.
    
Das Paaren zweier Pools, das nicht diesen Empfehlungen entspricht, wird weder durch den Topologie-Generator noch durch die Topologieüberprüfung verhindert. Der Topologie-Generator lässt z. B. die Paarung eines Enterprise Edition-Pools mit einem Standard Edition-Pool zu. Diese Arten von Kopplungen werden jedoch nicht unterstützt.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Beziehungen zwischen Sicherungsregistrierungsstellen und Survivable Branch Appliances

Zusätzlich zur Bereitstellung von Notfallwiederherstellungsfunktionen dienen zwei gepaarte Pools als Sicherungsregistrierungsstellen füreinander. Jeder Pool kann die Sicherung für nur einen anderen Front-End-Pool sein.
  
Obwohl sicherungsbeziehungen zwischen zwei Front-End-Pools 1:1 und symmetrisch sein müssen, kann jeder Front-End-Pool auch die Sicherungsregistrierungsstelle für eine beliebige Anzahl von Survivable Branch Appliances sein.
  
Beachten Sie, dass Skype for Business die Notfallwiederherstellung nicht auf Benutzer ausdehnt, die in einer Survivable Branch Appliance verwaltet werden. Wenn ein Front-End-Pool, der als Sicherung für eine Survivable Branch Appliance dient, ausfällt, wechseln benutzer, die bei der Survivable Branch Appliance angemeldet sind, in den Ausfallsicherheitsmodus, obwohl Benutzer, die im Front-End-Pool verwaltet werden, nicht zum Front-End-Sicherungspool wechseln.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Wiederherstellungszeit für Poolfailover und Poolfailback

Für Poolfailover und Poolfailback beträgt das Entwicklungsziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 15-20 Minuten. Dies ist die Zeit, die für das Failover erforderlich ist, nachdem Administratoren festgestellt haben, dass ein Notfall aufgetreten ist, und die Failoverprozeduren gestartet haben. Es umfasst weder die Zeit für Administratoren, die Situation zu bewerten und eine Entscheidung zu treffen, noch die Zeit, zu der sich Benutzer nach Abschluss des Failovers erneut anmelden müssen.
  
Bei Poolfailover und Poolfailback beträgt das Entwicklungsziel für das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO) 5 Minuten. Dies definiert die Zeitspanne, in der Daten aufgrund des Notfalls und aufgrund der Replikationswartezeit des Backupdienstes verloren gehen können. Wenn beispielsweise ein Pool um 10:00 Uhr ausfällt und das RPO 5 Minuten beträgt, werden daten zwischen 9:55 Uhr in den Pool geschrieben. und 10:00 Uhr . möglicherweise nicht in den Sicherungspool repliziert und wäre verloren gegangen.
  
Bei allen RTO- und RPO-Nummern in diesem Dokument wird davon ausgegangen, dass sich die beiden Rechenzentren in derselben Weltregion befinden und einen Transport mit hoher Geschwindigkeit und geringer Latenz zwischen den beiden Standorten aufweisen. Diese Zahlen werden für einen Pool mit 40.000 gleichzeitig aktiven Benutzern und 200.000 Benutzern für Skype for Business in Bezug auf ein vordefiniertes Benutzermodell gemessen, bei dem kein Backlog bei der Datenreplikation vorhanden ist. Sie unterliegen Änderungen basierend auf Leistungstests und Validierungen.
  
## <a name="central-management-store-failover"></a>Failover des zentralen Verwaltungsspeichers

Der zentrale Verwaltungsspeicher enthält Konfigurationsdaten zu den Servern und Diensten in Ihrer Bereitstellung. Jede Skype for Business Server Bereitstellung umfasst einen zentralen Verwaltungsspeicher, der vom Back-End-Server eines Front-End-Pools gehostet wird.
  
Wenn Sie den Pool koppeln, der den zentralen Verwaltungsspeicher hostet, wird im Sicherungspool eine Sicherungsdatenbank für den zentralen Verwaltungsspeicher eingerichtet. Zu jedem Zeitpunkt ist eine der beiden Zentralen Verwaltungsspeicherdatenbanken aktiv, die andere ist ein Standbymodus. Der Inhalt wird vom Sicherungsdienst aus der aktiven Datenbank in den Standbymodus repliziert.
  
![Zeigt zwei Front-End-Pools an, einen mit dem aktiven CMS-Speicher und den anderen mit dem passiven Sicherungs-CMS-Speicher.](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Während eines Poolfailovers, das den Pool umfasst, der den zentralen Verwaltungsspeicher hostet, müssen Sie einen Failover des zentralen Verwaltungsspeichers ausführen, bevor Sie einen Failover für den Front-End-Pool ausführen.
  
Nach der Reparatur des Notfalls ist es nicht erforderlich, einen Failback des zentralen Verwaltungsspeichers durchzuführen. Der zentrale Verwaltungsspeicher kann in dem Pool verbleiben, zu dem sie fehlgeschlagen sind.
  
Die Engineeringziele für das Failover des zentralen Verwaltungsspeichers sind 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) und 5 Minuten für das Ziel des Wiederherstellungspunkts (Recovery Point Objective, RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Datensicherheit bei der Kopplung von Front-End-Pools

Der Sicherungsdienst überträgt kontinuierlich Benutzerdaten und Konferenzinhalte zwischen zwei front-End-Paarpools. Die Benutzerdaten enthalten SIP-URIs des Benutzers sowie Konferenzpläne, Kontaktlisten und Einstellungen. Konferenzinhalte umfassen Microsoft PowerPoint Uploads sowie Whiteboards, die in Konferenzen verwendet werden.
  
Aus dem Quellpool werden diese Daten aus dem lokalen Speicher exportiert, gezippt und dann an den Zielpool übertragen, wo sie entpackt und in den lokalen Speicher importiert werden. Der Sicherungsdienst geht davon aus, dass sich die Kommunikationsverbindung zwischen den beiden Rechenzentren innerhalb des Unternehmensnetzwerks befindet, das vor dem Internet geschützt ist. Es verschlüsselt weder die übertragenen Daten zwischen den beiden Rechenzentren, noch werden die Daten systemintern in einem sicheren Protokoll wie HTTPS gekapselt. Daher ist ein Man-in-the-Middle-Angriff von internen Mitarbeitern innerhalb des Unternehmensnetzwerks möglich.
  
Jedes Unternehmen, das Skype for Business Server in mehreren Rechenzentren bereitstellt und die Notfallwiederherstellungsfunktion verwendet, muss sicherstellen, dass der Datenverkehr zwischen Rechenzentren durch das Unternehmensintranet geschützt wird. Unternehmen, die sich um internen Angriffsschutz kümmern, müssen die Kommunikationsverbindungen zwischen den Rechenzentren schützen. Dies ist eine Standardanforderung, die auch viele andere Arten von vertraulichen Unternehmensdaten unterstützt, die zwischen Rechenzentren übertragen werden.
  
Das Risiko von Man-in-the-Middle-Angriffen innerhalb des Unternehmensnetzwerks besteht zwar, doch ist es im Vergleich zur Gefährdung des Datenverkehrs im Internet relativ begrenzt. Insbesondere sind die vom Sicherungsdienst verfügbar gemachten Benutzerdaten (z. B. SIP-URIs) für alle Mitarbeiter innerhalb des Unternehmens über andere Mittel wie das globale Adressbuch oder andere Verzeichnissoftware allgemein verfügbar. Daher sollten Sie sich auf die Sicherung des WAN zwischen den beiden Rechenzentren konzentrieren, wenn der Sicherungsdienst zum Kopieren von Daten zwischen den beiden gekoppelten Pools verwendet wird.
  
### <a name="mitigating-security-risks"></a>Verringern von Sicherheitsrisiken

Sie haben viele Möglichkeiten, den Sicherheitsschutz für den Datenverkehr des Sicherungsdiensts zu verbessern. Dies reicht von der Einschränkung des Zugriffs auf die Rechenzentren bis zum Sichern des WAN-Transports zwischen den beiden Rechenzentren. In den meisten Fällen verfügen Unternehmen, die Skype for Business Server bereitstellen, möglicherweise bereits über die erforderliche Sicherheitsinfrastruktur. Für Unternehmen, die nach Anleitungen suchen, bietet Microsoft eine Lösung als Beispiel für die Erstellung einer sicheren IT-Infrastruktur. Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) . 
  
Wir implizieren weder, dass es sich um die einzige Lösung handelt, noch implizieren wir, dass es sich um die bevorzugte Lösung für Skype for Business Server handelt. Es wird empfohlen, dass Unternehmenskunden die Lösung basierend auf ihrer IT-Sicherheitsinfrastruktur und ihren Anforderungen für ihre spezifischen Anforderungen auswählen. In der Beispiellösung von Microsoft werden IPSec und Gruppenrichtlinien für die Server- und Domänenisolation verwendet.
  
Eine weitere mögliche Lösung besteht darin, IPSec nur zur Sicherung der vom Sicherungsdienst selbst gesendeten Daten zu verwenden. Wenn Sie diese Methode auswählen, sollten Sie die IPSec-Regeln für das SMB-Protokoll für die folgenden Server konfigurieren, wobei Pool A und Pool B zwei front-End-Paarpools sind.
  
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool A bis zur Datei Store von Pool B verwendet.
    
- Der SMB-Dienst (TCP/445) von jedem Front-End-Server in Pool B bis zur dateibasierten Store von Pool A verwendet.
    
> [!CAUTION]
>  IPsec ist nicht als Ersatz für die Sicherheit auf Anwendungsebene gedacht, z. B. SSL/TLS. Ein Vorteil der Verwendung von IPsec besteht darin, dass es Netzwerkdatenverkehr für vorhandene Anwendungen bereitstellen kann, ohne sie ändern zu müssen. Unternehmen, die nur den Transport zwischen den beiden Rechenzentren sichern möchten, sollten sich bei ihren jeweiligen Netzwerkhardwareanbietern nach Möglichkeiten zum Einrichten sicherer WAN-Verbindungen mithilfe der Geräte des Anbieters informieren.
  
## <a name="see-also"></a>Siehe auch

[Bereitstellen von front-End-Paarpools für die Notfallwiederherstellung in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)