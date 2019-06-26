---
title: Planen des Upgrades auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Zusammenfassung: informieren Sie sich über die Aspekte, die Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 0f7473bac98ede76763a3f5bda8aee3484c3c03f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222131"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen des Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: informieren Sie sich über die Aspekte, die Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)Center unter: herunter.
  
Im Rahmen Ihres Plans für ein Upgrade auf Skype for Business Server 2015 verwenden Sie dieses Thema, um die empfohlenen Upgrade-Pfade für Skype for Business Server 2015, die Funktionsweise des in-Place-Upgrades, die unterstützten Koexistenz-Szenarien und die Funktionsweise des Upgrade-Prozesses zu verstehen. sieht so aus.

> [!NOTE]
> In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Nebeneinander koexistieren wird unterstützt, lesen Sie [Migration zu Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) , um weitere Informationen zu erhalten.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Upgrade-Pfade für Skype for Business Server 2015

 Verwenden Sie die folgenden Upgrade-Pfade, um von lync Server 2013, lync Server 2010 oder Office Communications Server 2007 R2 auf Skype for Business Server 2015 zu aktualisieren:
  
> [!CAUTION]
> Bei direkten Upgrades werden Konferenzverzeichnisse automatisch von Lync Server 2013 zu Skype for Business Server 2015 verschoben. Wenn Sie jedoch beabsichtigen, die Konferenzverzeichnisse manuell zu verschieben, ist es sehr wichtig, dass Sie die Skype for Business Server 2015-Verwaltungsshell verwenden. Wenn Sie versuchen, die Konferenzverzeichnisse mithilfe der Lync Server 2013-Verwaltungsshell von Lync Server 2013 zu Skype for Business Server 2015 zu verschieben, kann es zu Datenverlust kommen. Im Allgemeinen gilt Folgendes: Immer dann, wenn Sie in beliebiger Kapazität mit Skype for Business Server 2015 arbeiten, sollten Sie die Skype for Business Server 2015-Toolsammlung verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Zum Upgrade verwenden Sie den Skype for Business Server-Topologie-Generator und das neue in-Place-Upgrade-Feature auf jedem der Server, die dem Pool zugeordnet sind. Detaillierte Schritte finden Sie unter [Planen des Upgrades von lync Server 2013 auf Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) und [Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + Lync Server 2013 (dualer Modus)  <br/> |Aktualisieren Sie zunächst auf lync Server 2013, und führen Sie dann ein Upgrade auf Skype for Business Server 2015 mithilfe des neuen in-Place-Upgrades durch. Wenn Ihre Topologie aber primär Lync Server 2010 umfasst, können Sie auch ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 und dann direkt ein Upgrade auf Skype for Business Server 2015 durchführen. In diesem Fall könnten Sie das direkte Upgrade nicht nutzen und würden die direkte Koexistenz zwischen Lync Server 2010 und Skype for Business Server 2015 verwenden. Dreifaches Vorhandensein wird nicht unterstützt, eine Koexistenz dagegen schon.  <br/> |
|Lync Server 2010  <br/> |Wählen Sie einen neuen Skype for Business Server 2015-Pool aus und migrieren Sie dann Benutzer zu diesem neuen Pool. Anschließend können Sie den alten Lync Server 2010-Pool außer Betrieb nehmen. Ein Upgrade von Lync Server 2010 auf Skype for Business Server 2015 ist ähnlich wie ein Upgrade von Lync Server 2010 auf Lync Server 2013. Weitere Informationen finden Sie unter [Migration von lync Server 2010 zu lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie zwischen zwei Optionen: <br/>  Einrichten einer neuen Skype for Business Server 2015-Umgebung <br/>  Oder wenn Ihre Hardware und Software die Anforderungen für Skype for Business Server 2015 erfüllt, aktualisieren Sie auf lync Server 2013, und aktualisieren Sie dann auf Skype for Business Server 2015, indem Sie das neue in-Place-Upgrade-Feature verwenden. Weitere Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) und [Migration von Office Communications Server 2007 R2 zu lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird in Skype for Business Server 2015 unterstützt, wird aber in lync Server 2013 nicht unterstützt. Wenn Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen möchten, muss der Pool zuerst auf Skype for Business Server 2015 mithilfe der in-Place-Upgrade-Methode aktualisiert werden, wie in diesem Dokument beschrieben. Anschließend können Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen, indem Sie [auf SQL Server 2014 aktualisieren](https://msdn.microsoft.com/en-us/library/bb677622%28v=sql.120%29.aspx). Weitere Informationen zu den Datenbankanforderungen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planung eines Upgrades von Lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Mit dem neuen in-Place-Upgrade-Feature können Sie lync Server 2013-Systeme auf Skype for Business Server 2015 aktualisieren. Das in-Place-Upgrade bietet eine Lösung mit einem Mausklick, mit der Zertifikate gesichert, Server Komponenten deinstalliert, lokale Datenbanken aktualisiert und die Funktionen von Skype for Business Server 2015 installiert werden. Das in-Place-Upgrade soll vorhandene Hardware-und Server Investitionen beibehalten und die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 reduzieren.
  
> [!NOTE]
> Bei einem direkten Upgrade können Sie die gleiche Hardware beim Upgrade auf Skype for Business Server verwenden. Bei der Wiederverwendung der gleichen Hardware dürfen Sie jedoch nicht von derselben Leistungsfähigkeit ausgehen. Sie sollten nicht davon ausgehen, dass die Leistungs Lasten für lync Server 2013 und Skype for Business Server 2015 identisch sind. 
  
> [!NOTE]
> Das direkte Upgrade unterstützt keine Hochverfügbarkeit oder Disaster Recovery für Skype for Business Server. 
  
Das direkte Upgrade umfasst das offline schalten des lync Server 2013-Pools und die Aktualisierung auf einen Skype for Business Server 2015-Pool. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines Plans für ein direktes Upgrade

Stellen Sie einen Plan auf, der Folgendes umfasst:
  
1. Verständnis für Ihre aktuelle Topologie.
    
    > [!NOTE]
    > Stellen Sie sicher, dass Sie das LRS-Verwaltungstool für lync Server 2013 deinstallieren, bevor Sie ein direktes Upgrade ausführen. Das LRS-Verwaltungs Tool für lync Server 2013 kann nicht mit Skype for Business Server 2015 koexistieren. Installieren Sie nach dem Ausführen des direkten Upgrades das neue LRS-Verwaltungstool. Weitere Informationen finden Sie unter [Microsoft lync Room System administrative Web Portal für Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) .
  
2. Der primäre Pool für das Upgrade.
    
3. Die Entscheidung darüber, ob ein Upgrade der Datenbanken für die Archivierung und Überwachung durchgeführt oder neue Datenbanken erstellt werden sollen.
    
4. Die verwendete Methode für direkte Upgrades: Offline oder durch Verschieben von Benutzern. Wenn Sie Benutzer verschieben, müssen Sie auch die mit dem primären Pool verknüpften globalen Konferenzverzeichnisse migrieren. 
    
5. Einen Kommunikationsplan für betroffene Benutzer.
    
6. Einen Plan zur Sicherung im Falle eines fehlgeschlagenen Upgrades.
    
Alle dem primären Pool angehörenden Benutzer können die Dienste während des Upgrades nicht nutzen. Wenn Sie über einen funktionsfähigen sekundären Pool verfügen, können Sie diese Benutzer vor dem Upgrade dorthin verschieben, damit sie nicht von der Ausfallzeit während des Upgrades betroffen sind. Nachdem Sie das Upgrade durchgeführt haben, verschieben Sie die Benutzer wieder in den primären Pool.
  
### <a name="in-place-upgrade-methods"></a>Methoden für direkte Upgrades

Es gibt zwei Methoden für direkte Upgrades: 
  
- Bei der ersten Methode werden die Benutzer verschoben, so entsteht für sie keine Ausfallzeit. 
    
- Bei der Offline-Methode entsteht für die Benutzer eine Ausfallzeit.
    
Wie empfehlen daher, dass ein Upgrade mithilfe der Offline-Methode während einer Wartung durchgeführt wird und die Benutzer über die geplante Ausfallzeit informiert werden.
  
> [!NOTE]
> Beim Upgrade eines gekoppelten Pools in Lync Server 2013, bei dem ein Upgrade beider Pools auf Skype for Business Server 2015 ausgeführt werden soll, stellen Sie sicher, dass das Upgrade des zweiten Pools unmittelbar nach dem Upgrade des ersten Pools erfolgt. Wenn ein Pool mit Lync Server 2013 und der zweite Pool mit Skype for Business Server 2015 ausgeführt wird, sind die Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool unter Version 2013 und der zweite unter Version 2015 ausgeführt wird und es zu einem Notfall kommt, kann es zu Datenverlusten kommen, da ein Pool-Failover im Notfallmodus nicht unterstützt wird, wenn ein Poolpaar nicht unter der gleichen Version ausgeführt wird. 
  
#### <a name="in-place-upgrade-offline-method"></a>Offline-Methode für direkte Updates

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Pools verschieben möchten. Während des Upgrades können die Benutzer keine lync-oder Skype for Business-Dienste verwenden. 
  
Im folgenden Diagramm ist eine Übersicht über diesen Prozess dargestellt.
  
![Lync 2013 an Skype-Offlinebenutzer](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie über gepaarte Pools verfügen, lösen Sie die Paarung nicht vor dem Upgrade. 
  
Nachdem Sie mit dem Upgrade eines Serverpools begonnen haben, müssen Sie das Upgrade des gesamten Pools vervollständigen. Skype for Business Server unterstützt nicht, dass nur ein Teil des Pools aktualisiert wird. 
  
#### <a name="move-users-method-no-user-downtime"></a>Methode der Verschiebung von Benutzern (keine Ausfallzeit für Benutzer)
<a name="bkmk_MoveUsersMethod"> </a>

Zur Verwendung dieser Methode verschieben Sie die Benutzer in einen anderen Pool, bevor Sie mit dem Upgrade beginnen. Während des Upgrades können Benutzer lync-Dienste verwenden. Nachdem Sie in den aktualisierten Pool verschoben wurden, kann Skype for Business verwendet werden. Im folgenden Diagramm sehen Sie einen Überblick über diesen Prozess.
  
> [!IMPORTANT]
> Im Rahmen dieser Methode müssen Sie auch die mit dem primären Pool verknüpften globalen Konferenzverzeichnisse migrieren. PSTN-Einwahlkonferenzen lösen weiterhin die ConferenceID in den aktualisierten Pool und nicht in den gepaarten Pool auf. Daher müssen die Konferenzverzeichnisse verschoben werden, wenn die im Pool geplanten PSTN-Konferenzen während des Upgrades weiterhin zugänglich sein sollen. 
  
![Schwimmbahn-Diagramm, das Benutzer zeigt, die in einen anderen Pool verschoben werden, bevor der Pool ein Upgrade erhält, und anschließend wieder zurückgeholt werden.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Benutzer für ein Hardware-Upgrade verschieben
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware die [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)nicht erfüllt, richten Sie eine neue Skype for Business Server 2015-Umgebung ein, und verschieben Sie die Benutzer dorthin. Im folgenden Diagramm ist eine Übersicht über diesen Prozess für ein Upgrade von Lync Server 2010 dargestellt. 
  
![Schwimmbahn-Diagramm, das die Benutzer im primären Front-End-Pool des Lync-Servers zeigt, die in Skype for Business Server 2015 verschoben werden, und den außer Betrieb gesetzten Lync-Server-Pool.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Prozess des direkten Upgrades

 Führen Sie die folgenden Schritte aus, um ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchzuführen:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass alle Dienste, für die ein Upgrade ausgeführt werden soll, aktiv ausgeführt werden.
    
3. Führen Sie ein Upgrade der Topologiedatei mithilfe des Topologie-Generator durch und veröffentlichen Sie diese.
    
4. Unterbrechen Sie alle Dienste der Front-End-Server.
    
5. Installieren Sie die für Skype for Business Server erforderlichen neuen Voraussetzungen.
    
6. Starten Sie das direkte Upgrade auf jedem Front-End-Server.
    
7. Nach Abschluss des Upgrades müssen Sie alle Dienste neu starten.
    
   - Starten Sie für alle Front-End-Pools mithilfe des Befehls Start-CsPool neu.
    
   - Verwenden Sie Start-CSWindowsService für Server, die keine Front-End-Server sind.
    
> [!NOTE]
>  Wenn Sie kein Upgrade für die bereits vorhandenen Datenbanken zur Archivierung und Überwachung durchführen möchten, entfernen Sie die Abhängigkeit, bevor Sie ein Upgrade der Topologie durchführen. Wenn Sie neue Datenbanken zur Archivierung und Überwachung erstellen möchten, können Sie einen neuen SQL-Speicher erstellen und ihn dem Pool zuweisen. Die Schritte zur Vorgehensweise finden Sie im Thema[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > in-Place-Upgrade unterstützt keine Hochverfügbarkeit oder Disaster Recovery für Skype for Business Server. Um zu verhindern, dass die Dienste der Benutzer unterbrechen, verwenden Sie die [Methode zum Verschieben von Benutzern (keine Ausfallzeit des Benutzers)](upgrade.md#bkmk_MoveUsersMethod) , um ein Upgrade durchzuführen. #a0 während des Upgradevorgangs wird das XDS-Replikat im lokalen freigegebenen Ordner auf dem Laufwerk mit dem meisten freien Speicherplatz abgelegt. Wird dieses Laufwerk später entfernt, treten unter Umständen Probleme auf, zum Beispiel starten Dienste möglicherweise nicht.
  
### <a name="upgrade-order"></a>Upgrade-Reihenfolge

Aktualisieren Sie die Topologie von innen nach außen. Führen Sie zunächst ein Upgrade aller Pools durch, fahren Sie dann mit den Edgeservern fort und führen Sie zum Schluss ein Upgrade für den zentralen Verwaltungsspeicher (CMS, Central Management Store) durch. 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie die Kerberos-Konten neu zuweisen und das Kennwort nach Abschluss eines direkten Upgrades zurücksetzen. Informationen dazu finden Sie unter [Einrichten der Kerberos-Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung für die Koexistenz mit lync Server 2013 und lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie Lync Server 2013 oder Lync Server 2010 ausführen, es können jedoch nicht alle drei Lösungen in derselben Topologie vorhanden sein.
  
Wenn eine Koexistenz zwischen Lync Server 2010 und Lync Server 2013 vorliegt, wird ein Upgrade der gesamten Topologie auf Lync Server 2013 sowie ein anschließendes Upgrade auf Skype for Business Server 2015 mit der Funktion für direkte Upgrades empfohlen. Weitere Informationen finden Sie unter [Migration von lync Server 2010 zu lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Wenn es sich bei Ihrer Topologie primär um Lync Server 2010 handelt, führen Sie ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durch, bevor Sie ein Upgrade der Topologie auf Skype for Business Server 2015 durchführen. In diesem Fall können Sie die Vorteile der Funktion für direkte Upgrades nicht nutzen und verfügen über eine Koexistenz-Topologie zwischen Lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die Koexistenz-Unterstützung von Skype for Business Server 2015 mit lync Server 2013 und lync Server 2010.
  
![Ein Diagramm, das die Koexistenzunterstützung für Skype for Business Server 2015 mit entweder Lync Server 2013 oder Lync Server 2010 zeigt.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch-Anwendung und vorhandenem Survivable Branch Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 unterstützt kein in-Place-Upgrade einer Survivable Branch Appliance (SBA) oder eines Survivable Branch Servers (SBS).
  
Die Koexistenz zwischen Skype for Business Server-Rechenzentren mit Lync Server 2010 oder Lync Server 2013 SBA/SBS wird jedoch unterstützt. 
  
Wenn Sie ein direktes Upgrade eines Lync Server 2013-Front-End (FE)-Pools mit einem zugeordneten Zweigstellenstandort planen, können die vorhandenen Benutzer auf dem Lync Server 2013 SBA/SBS verbleiben. Während des Upgrades wechseln die SBA/SBS-Benutzer in den Ausfallsicherheitsmodus und kehren nach Abschluss des Upgrades in den normalen Funktionsmodus zurück. Weitere Informationen über die Benutzererfahrung während des Stabilitäts Modus finden Sie unter Features von [Branch-Site-Resilienz in lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Wenn Sie eine lync Server 2010-Topologie zu Skype for Business Server 2015 migrieren, muss die SBA/SBS erneut zur Topologie hinzugefügt werden, ähnlich wie bei der Migration zu lync Server 2013. Die erforderlichen Schritte finden Sie unter [Verbinden von Survivable Branch Appliance mit dem lync Server 2013-Front-End-Pool](https://technet.microsoft.com/library/jj688026.aspx).
  
Für Koexistenz-Topologien von lync Server 2010 und lync Server 2013 richten Sie sich zunächst an die Empfehlungen im Abschnitt "Unterstützung für die Koexistenz mit lync Server 2013 und lync Server 2010" aus.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Environmental requirements for Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
