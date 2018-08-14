---
title: Planen des Upgrades auf Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Zusammenfassung: Informationen Sie über die Dinge, dass Sie bei der Planung eines Upgrades auf Skype für Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 15f8ba6568fc4ca26d1c9fd33a59a026a34def33
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009144"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen des Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: Informationen Sie über die Dinge, dass Sie bei der Planung eines Upgrades auf Skype für Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Im Rahmen des Projektplans zum Upgraden auf Skype für Business Server 2015, verwenden Sie dieses Thema um zu verstehen, wie die empfohlene Aktualisierungspfade zu Skype für Business Server 2015, die In-Place Upgrade funktioniert, was die unterstützte Koexistenzszenarien sind, und den Upgradeprozess sieht folgendermaßen aus.

> [!NOTE]
> Compliance-Upgrades in Skype für Business Server 2015 verfügbar waren, jedoch werden in Skype für Business Server 2019 nicht mehr unterstützt. Nebeneinander Koexistenz unterstützt wird, finden Sie weitere Informationen unter [Migration zu Skype für Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) .
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Aktualisierungspfade zu Skype für Business Server 2015

 Wenn von Lync Server 2013, Lync Server 2010 oder Office Communications Server 2007 R2 auf Skype für Business Server 2015 aktualisieren, verwenden Sie die folgenden Aktualisierungspfade:
  
> [!CAUTION]
> Bei direkten Upgrades werden Konferenzverzeichnisse automatisch von Lync Server 2013 zu Skype for Business Server 2015 verschoben. Wenn Sie jedoch beabsichtigen, die Konferenzverzeichnisse manuell zu verschieben, ist es sehr wichtig, dass Sie die Skype for Business Server 2015-Verwaltungsshell verwenden. Wenn Sie versuchen, die Konferenzverzeichnisse mithilfe der Lync Server 2013-Verwaltungsshell von Lync Server 2013 zu Skype for Business Server 2015 zu verschieben, kann es zu Datenverlust kommen. Im Allgemeinen gilt Folgendes: Immer dann, wenn Sie in beliebiger Kapazität mit Skype for Business Server 2015 arbeiten, sollten Sie die Skype for Business Server 2015-Toolsammlung verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Verwenden Sie zum Aktualisieren der Skype für Business Server-Topologie-Generator und das neue Feature für In-Place Upgrade auf jedem Server, der dem Pool zugeordnet. Ausführliche Schritte finden Sie unter [Aktualisieren von Lync Server 2013 für die Skype für Business Server 2015 planen](upgrade.md#BKMK_PlanUpgradeFromLync2013) und [Durchführen eines Upgrades auf Skype für Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (dualer Modus)  <br/> |Erstens Durchführen eines Upgrades auf Lync Server 2013, und dann auf Aktualisieren Skype für Business Server 2015 mithilfe des neuen Features In-Place Upgrade. Wenn Ihre Topologie aber primär Lync Server 2010 umfasst, können Sie auch ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 und dann direkt ein Upgrade auf Skype for Business Server 2015 durchführen. In diesem Fall könnten Sie das direkte Upgrade nicht nutzen und würden die direkte Koexistenz zwischen Lync Server 2010 und Skype for Business Server 2015 verwenden. Dreifaches Vorhandensein wird nicht unterstützt, eine Koexistenz dagegen schon.  <br/> |
|Lync Server 2010  <br/> |Wählen Sie einen neuen Skype for Business Server 2015-Pool aus und migrieren Sie dann Benutzer zu diesem neuen Pool. Anschließend können Sie den alten Lync Server 2010-Pool außer Betrieb nehmen. Ein Upgrade von Lync Server 2010 auf Skype for Business Server 2015 ist ähnlich wie ein Upgrade von Lync Server 2010 auf Lync Server 2013. Finden Sie unter [Migration von Lync Server 2010 zu Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie zwischen zwei Optionen: <br/>  Richten Sie eine neue Skype für Business Server 2015-Umgebung. <br/>  Auch wenn Ihre Hardware und Software die Anforderungen für Skype für Business Server 2015 erfüllen, Durchführen eines Upgrades auf Lync Server 2013 und Upgraden Sie dann mithilfe des neuen Features In-Place Upgrade für Business Server 2015 auf Skype. Weitere Informationen finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](requirements-for-your-environment/server-requirements.md) und [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird unterstützt Skype für Business Server 2015 jedoch nicht in Lync Server 2013 unterstützt wird. Wenn Sie von SQL Server 2012 auf SQL Server 2014 aktualisieren möchten muss dann der Pool zuerst auf Skype für Business Server 2015 mithilfe der In-Place Upgrade-Methode, wie in diesem Dokument beschrieben aktualisiert werden. Sie können dann aktualisieren von SQL Server 2012, um den SQL Server 2014, finden Sie unter [Aktualisieren auf SQL Server 2014](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Weitere Informationen zum datenbankanforderungen finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planung eines Upgrades von Lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Lync Server 2013-Systeme auf Skype für Business Server 2015 mithilfe der neuen Funktion In-Place Upgrade aktualisieren. Direktes Upgrade bietet eine per Mausklick-Lösung, die Zertifikate sichert, Server-Komponenten deinstalliert, lokale Datenbanken aktualisiert und die Skype für Business Server 2015 Rollen installiert. Direktes Upgrade soll vorhandener Hardware und Server Investitionen, Verringerung der Kosten für allgemeinen zum Bereitstellen von Skype für Business Server 2015 beibehalten.
  
> [!NOTE]
> In-Place Upgrade können Sie die gleiche Hardware beim Upgrade auf Skype für Business Server verwenden. Bei der Wiederverwendung der gleichen Hardware dürfen Sie jedoch nicht von derselben Leistungsfähigkeit ausgehen. Sie sollten davon ausgehen, dass die Leistung Lasten für Lync Server 2013 und Skype für Business Server 2015 identisch sein. 
  
> [!NOTE]
> Direktes Upgrade unterstützt keine hohe Verfügbarkeit oder Disaster Recovery für Skype für Business Server. 
  
Direktes Upgrade umfasst Offlineschalten von Lync Server 2013-Pool, und aktualisieren es auf einen Skype für Business Server 2015 Pool. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines Plans für ein direktes Upgrade

Stellen Sie einen Plan auf, der Folgendes umfasst:
  
1. Kenntnis der aktuellen Topologie.
    
    > [!NOTE]
    > Achten Sie darauf, dass LRS-Verwaltungstool für Lync Server 2013 vor dem Ausführen des In-Place Upgrade zu deinstallieren. Die LRS-Verwaltungstool für Lync Server 2013 können nicht mit Skype für Business Server 2015 verwendet werden. Installieren Sie nach dem Ausführen der In-Place Upgrade der neuen LRS-Verwaltungstool, finden Sie unter [Microsoft Lync Raum System Administrative Webportal für Skype für Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. Der primäre Pool für das Upgrade.
    
3. Die Entscheidung darüber, ob ein Upgrade der Datenbanken für die Archivierung und Überwachung durchgeführt oder neue Datenbanken erstellt werden sollen.
    
4. Die verwendete Methode für direkte Upgrades: Offline oder durch Verschieben von Benutzern. Wenn Sie Benutzer verschieben, müssen Sie auch die mit dem primären Pool verknüpften globalen Konferenzverzeichnisse migrieren. 
    
5. Einen Kommunikationsplan für betroffene Benutzer.
    
6. Einen Plan zur Sicherung im Falle eines fehlgeschlagenen Upgrades.
    
Alle dem primären Pool angehörenden Benutzer können die Dienste während des Upgrades nicht nutzen. Wenn Sie über einen funktionsfähigen sekundären Pool verfügen, können Sie diese Benutzer vor dem Upgrade dorthin verschieben, damit sie nicht von der Ausfallzeit während des Upgrades betroffen sind. Verschieben Sie die Benutzer nach dem Upgrade wieder in den primären Pool aus.
  
### <a name="in-place-upgrade-methods"></a>Methoden für direkte Upgrades

Es gibt zwei Methoden für direkte Upgrades: 
  
- Bei der ersten Methode werden die Benutzer verschoben, so entsteht für sie keine Ausfallzeit. 
    
- Bei der Offline-Methode entsteht für die Benutzer eine Ausfallzeit.
    
Wie empfehlen daher, dass ein Upgrade mithilfe der Offline-Methode während einer Wartung durchgeführt wird und die Benutzer über die geplante Ausfallzeit informiert werden.
  
> [!NOTE]
> Beim Upgrade eines gekoppelten Pools in Lync Server 2013, bei dem ein Upgrade beider Pools auf Skype for Business Server 2015 ausgeführt werden soll, stellen Sie sicher, dass das Upgrade des zweiten Pools unmittelbar nach dem Upgrade des ersten Pools erfolgt. Wenn ein Pool mit Lync Server 2013 und der zweite Pool mit Skype for Business Server 2015 ausgeführt wird, sind die Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool unter Version 2013 und der zweite unter Version 2015 ausgeführt wird und es zu einem Notfall kommt, kann es zu Datenverlusten kommen, da ein Pool-Failover im Notfallmodus nicht unterstützt wird, wenn ein Poolpaar nicht unter der gleichen Version ausgeführt wird. 
  
#### <a name="in-place-upgrade-offline-method"></a>Offline-Methode für direkte Updates

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Pools verschieben möchten. Während des Upgrades werden Benutzer nicht Lync oder Skype für BusinessServices verwendet werden können. 
  
Im folgenden Diagramm ist eine Übersicht über diesen Prozess dargestellt.
  
![Lync 2013 an Skype-Offlinebenutzer](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie über gepaarte Pools verfügen, lösen Sie die Paarung nicht vor dem Upgrade. 
  
Nachdem Sie mit dem Upgrade eines Serverpools begonnen haben, müssen Sie das Upgrade des gesamten Pools vervollständigen. Skype für Business Server unterstützt nicht, müssen nur einen Teil des Pools aktualisiert. 
  
#### <a name="move-users-method-no-user-downtime"></a>Methode der Verschiebung von Benutzern (keine Ausfallzeit für Benutzer)
<a name="bkmk_MoveUsersMethod"> </a>

Zur Verwendung dieser Methode verschieben Sie die Benutzer in einen anderen Pool, bevor Sie mit dem Upgrade beginnen. Während des Upgrades können Benutzer Lync-Dienste verwenden. Nachdem sie in der aktualisierte Pool verschoben haben, können sie Skype für Unternehmen verwenden. Im folgenden Diagramm sehen Sie einen Überblick über diesen Prozess.
  
> [!IMPORTANT]
> Im Rahmen dieser Methode müssen Sie auch die mit dem primären Pool verknüpften globalen Konferenzverzeichnisse migrieren. PSTN-Einwahlkonferenzen lösen weiterhin die ConferenceID in den aktualisierten Pool und nicht in den gepaarten Pool auf. Daher müssen die Konferenzverzeichnisse verschoben werden, wenn die im Pool geplanten PSTN-Konferenzen während des Upgrades weiterhin zugänglich sein sollen. 
  
![Schwimmbahn-Diagramm, das Benutzer zeigt, die in einen anderen Pool verschoben werden, bevor der Pool ein Upgrade erhält, und anschließend wieder zurückgeholt werden.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Benutzer für ein Hardware-Upgrade verschieben
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware den [Anforderungen für Skype für Business Server 2015](requirements-for-your-environment/server-requirements.md)nicht erfüllt werden, richten Sie eine neue Skype für Business Server 2015 Umgebung, und verschieben Sie Benutzer vorhanden. Im folgenden Diagramm ist eine Übersicht über diesen Prozess für ein Upgrade von Lync Server 2010 dargestellt. 
  
![Schwimmbahn-Diagramm, das die Benutzer im primären Front-End-Pool des Lync-Servers zeigt, die in Skype for Business Server 2015 verschoben werden, und den außer Betrieb gesetzten Lync-Server-Pool.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Prozess des direkten Upgrades

 Aktualisieren von Lync Server 2013 zu Skype für Business Server 2015 mit den folgenden Schritten:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass alle Dienste, für die ein Upgrade ausgeführt werden soll, aktiv ausgeführt werden.
    
3. Führen Sie ein Upgrade der Topologiedatei mithilfe des Topologie-Generator durch und veröffentlichen Sie diese.
    
4. Unterbrechen Sie alle Dienste der Front-End-Server.
    
5. Installieren von neuen erforderlichen Komponenten für Skype für Business Server benötigt.
    
6.  Starten Sie das direkte Upgrade auf jedem Front-End-Server.
    
7. Nach Abschluss des Upgrades müssen Sie alle Dienste neu starten.
    
  - Starten Sie für alle Front-End-Pools mithilfe des Befehls Start-CsPool neu.
    
  - Verwenden Sie Start-CSWindowsService für Server, die keine Front-End-Server sind.
    
> [!NOTE]
>  Wenn Sie kein Upgrade für die bereits vorhandenen Datenbanken zur Archivierung und Überwachung durchführen möchten, entfernen Sie die Abhängigkeit, bevor Sie ein Upgrade der Topologie durchführen. Wenn Sie neue Datenbanken zur Archivierung und Überwachung erstellen möchten, können Sie einen neuen SQL-Speicher erstellen und ihn dem Pool zuweisen. Sie können die Schritte zum dazu im Thema[Durchführen eines Upgrades auf Skype für Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)suchen. > In-Place Upgrade unterstützt hohe Verfügbarkeit oder notfallwiederherstellung für Skype für Business Server nicht. Um zu vermeiden, Benutzer Dienste unterbrechen, verwenden Sie die [Benutzer verschieben-Methode (keine Benutzer Ausfallzeit)](upgrade.md#bkmk_MoveUsersMethod) zum Upgrade. > während des Upgrades das Xds-Replikat in der lokalen freigegebenen Ordner auf dem Laufwerk mit dem meisten freien Speicherplatz platziert wird. Wird dieses Laufwerk später entfernt, treten unter Umständen Probleme auf, zum Beispiel starten Dienste möglicherweise nicht.
  
### <a name="upgrade-order"></a>Upgrade-Reihenfolge

Aktualisieren Sie die Topologie von innen nach außen. Führen Sie zunächst ein Upgrade aller Pools durch, fahren Sie dann mit den Edgeservern fort und führen Sie zum Schluss ein Upgrade für den zentralen Verwaltungsspeicher (CMS, Central Management Store) durch. 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie die Kerberos-Konten neu zuweisen und das Kennwort nach Abschluss eines direkten Upgrades zurücksetzen. Weitere Informationen hierzu finden Sie unter [Einrichten der Kerberos-Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung für die Koexistenz mit Lync Server 2013 und Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie Lync Server 2013 oder Lync Server 2010 ausführen, es können jedoch nicht alle drei Lösungen in derselben Topologie vorhanden sein.
  
Wenn eine Koexistenz zwischen Lync Server 2010 und Lync Server 2013 vorliegt, wird ein Upgrade der gesamten Topologie auf Lync Server 2013 sowie ein anschließendes Upgrade auf Skype for Business Server 2015 mit der Funktion für direkte Upgrades empfohlen. Weitere Informationen finden Sie unter [Migration von Lync Server 2010 zu Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Wenn es sich bei Ihrer Topologie primär um Lync Server 2010 handelt, führen Sie ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durch, bevor Sie ein Upgrade der Topologie auf Skype for Business Server 2015 durchführen. In diesem Fall können Sie die Vorteile der Funktion für direkte Upgrades nicht nutzen und verfügen über eine Koexistenz-Topologie zwischen Lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die koexistenzunterstützung von Skype Business Server 2015 mit Lync Server 2013 und Lync Server 2010.
  
![Ein Diagramm, das die Koexistenzunterstützung für Skype for Business Server 2015 mit entweder Lync Server 2013 oder Lync Server 2010 zeigt.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch-Anwendung und vorhandenem Survivable Branch Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype für Business Server 2015 unterstützt keine direkte Aktualisierung Survivable Branch Appliance (SBA) oder einen Survivable Branch Server (SBS).
  
Die Koexistenz zwischen Skype for Business Server-Rechenzentren mit Lync Server 2010 oder Lync Server 2013 SBA/SBS wird jedoch unterstützt. 
  
Wenn Sie ein direktes Upgrade eines Lync Server 2013-Front-End (FE)-Pools mit einem zugeordneten Zweigstellenstandort planen, können die vorhandenen Benutzer auf dem Lync Server 2013 SBA/SBS verbleiben. Während des Upgrades wechseln die SBA/SBS-Benutzer in den Ausfallsicherheitsmodus und kehren nach Abschluss des Upgrades in den normalen Funktionsmodus zurück. Weitere Informationen zu der Benutzer wünschen während der ausfallsicherheitsmodus ist finden Sie unter [Branch-Site Resiliency Features in Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Wenn erneut hinzugefügt Migrieren einer Lync Server 2010-Topologie zu Skype für Business Server 2015, der SBA/SBS muss die Topologie, ähnlich wie die Migration zu Lync Server 2013. Lesen Sie [Verbinden Survivable Branch Appliance zu Lync Server 2013-Front-End-Pool](https://technet.microsoft.com/library/jj688026.aspx), für die erforderlichen Schritte.
  
Für Topologien Koexistenz von Lync Server 2010 und Lync Server 2013 angepasst werden zuerst die Empfehlungen im Abschnitt "Unterstützung für die Koexistenz mit Lync Server 2013 und Lync Server 2010" gestellt.
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Anforderungen an die Umgebung für Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)