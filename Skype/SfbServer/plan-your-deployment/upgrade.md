---
title: Planen eines Upgrades auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie beim Planen eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center unter herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 742a582c9945e495bf150a174f8bc80101f61f7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122369"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen eines Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie beim Planen eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center unter herunter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Verwenden Sie dieses Thema im Rahmen Ihres Plans zum Upgrade auf Skype for Business Server 2015, um die empfohlenen Upgradepfade für Skype for Business Server 2015, die Funktionsweise des In-Place-Upgrades, die unterstützten Koexistenzszenarien und das Aussehen des Upgradeprozesses zu verstehen.

> [!NOTE]
> In Skype for Business Server 2015 waren upgrades verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Die nebeneinander geschaltete Koexistenz wird unterstützt, weitere Informationen finden Sie unter [Migration to Skype for Business Server 2019.](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Upgradepfade für Skype for Business Server 2015

 Zum Upgrade von Lync Server 2013, Lync Server 2010 oder Office Communications Server 2007 R2 auf Skype for Business Server 2015 verwenden Sie die folgenden Upgradepfade:
  
> [!CAUTION]
> In-Place Upgrade verschiebt Konferenzverzeichnissen automatisch von Lync Server 2013 zu Skype for Business Server 2015. Wenn Sie jedoch planen, Konferenzverzeichnissen manuell zu verschieben, ist es sehr wichtig, die Skype for Business Server 2015-Verwaltungsshell zu verwenden. Wenn Sie versuchen, die Lync Server 2013-Verwaltungsshell zum Verschieben von Konferenzverzeichnissen von Lync Server 2013 zu Skype for Business Server 2015 zu verwenden, kann es zu Datenverlusten kommen. Im Allgemeinen sollten Sie, wenn Sie mit Skype for Business Server 2015 in beliebiger Kapazität arbeiten, den Skype for Business Server 2015-Toolsatz verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Verwenden Sie zum Upgrade den Skype for Business Server Topology Builder und das neue In-Place-Upgradefeature auf jedem server, der dem Pool zugeordnet ist. Ausführliche Schritte finden Sie unter Plan [to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) und Upgrade to Skype for Business Server [2015.](../deploy/upgrade-to-skype-for-business-server.md) <br/> |
|Lync Server 2010 + Lync Server 2013 (dualer Modus)  <br/> |Führen Sie zunächst ein Upgrade auf Lync Server 2013 und dann ein Upgrade auf Skype for Business Server 2015 mithilfe der neuen In-Place Upgradefunktion durch. Wenn Ihre Topologie jedoch primär lync Server 2010 ist, können Sie auch ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durchführen und dann ein direktes Upgrade auf Skype for Business Server 2015 durchführen. In diesem Fall können Sie das In-Place-Upgrade nicht nutzen und würden eine geradlinig koexistenz zwischen Lync Server 2010 und Skype for Business Server 2015 verwenden. Triexistenz wird nicht unterstützt, die Koexistenz wird jedoch unterstützt.  <br/> |
|Lync Server 2010  <br/> |Erstellen Sie einen neuen Skype for Business Server 2015-Pool, und migrieren Sie die Benutzer zu diesem neuen Pool. Anschließend können Sie den alten Lync Server 2010-Pool außer Betrieb lassen. Das Upgrade von Lync Server 2010 auf Skype for Business Server 2015 ähnelt dem Upgrade von Lync Server 2010 auf Lync Server 2013. Weitere [Informationen finden Sie unter Migration from Lync Server 2010 to Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie eine von zwei Optionen aus: <br/>  Richten Sie eine neue Skype for Business Server 2015-Umgebung ein. <br/>  Oder wenn Ihre Hardware und Software die Anforderungen für Skype for Business Server 2015 erfüllt, führen Sie ein Upgrade auf Lync Server 2013 und dann ein Upgrade auf Skype for Business Server 2015 mithilfe des neuen In-Place-Upgradefeatures durch. Weitere Informationen finden Sie unter [Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) und [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird in Skype for Business Server 2015 unterstützt, aber in Lync Server 2013 nicht unterstützt. Wenn Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen möchten, muss der Pool zunächst mithilfe der In-Place Upgrade-Methode wie in diesem Dokument beschrieben auf Skype for Business Server 2015 aktualisiert werden. Sie können dann ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen, siehe [Upgrade auf SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014). Weitere Informationen zu Datenbankanforderungen finden Sie unter [Server requirements for Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planen eines Upgrades von Lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Lync Server 2013-Systeme mithilfe der neuen In-Place Upgradefunktion auf Skype for Business Server 2015 aktualisieren. Das lokale Upgrade bietet eine Lösung mit einem Klick, mit der Zertifikate, Serverkomponenten deinstalliert, lokale Datenbanken aktualisiert und die Skype for Business Server 2015-Rollen installiert werden. Durch das "In-Place"-Upgrade werden vorhandene Hardware- und Serverinvestitionen beibehalten, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 reduziert werden.
  
> [!NOTE]
> In-Place Upgrade können Sie dieselbe Hardware beim Upgrade auf Skype for Business Server verwenden. Die Erneutvernendung derselben Hardware führt jedoch nicht zu derselben Leistungsfähigkeit. Sie sollten nicht erwarten, dass die Leistungslasten für Lync Server 2013 und Skype for Business Server 2015 identisch sind. 
  
> [!NOTE]
> In-Place Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. 
  
Beim "In-Place"-Upgrade wird der Lync Server 2013-Pool offline geschaltet und auf einen Skype for Business Server 2015-Pool aktualisiert. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines In-Place Upgradeplans

Erstellen Sie einen Plan mit:
  
1. Ein Verständnis Ihrer aktuellen Topologie.
    
    > [!NOTE]
    > Deinstallieren Sie unbedingt das LRS Admin Tool für Lync Server 2013, bevor Sie In-Place ausführen. Das LRS Admin Tool für Lync Server 2013 kann nicht mit Skype for Business Server 2015 zusammenarbeiten. Installieren Sie nach In-Place Upgrade das neue LRS Admin-Tool. Weitere Informationen finden Sie unter [Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015.](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. Der primäre Pool für das Upgrade.
    
3. Unabhängig davon, ob Sie die Archivierungs- und Überwachungsdatenbanken aktualisieren oder neue erstellen.
    
4. Die In-Place Upgrade-Methode, die Sie verwenden: Offline oder Benutzer verschieben. Im Rahmen von Move Users müssen Sie auch die globalen Konferenzverzeichnissen migrieren, die dem primären Pool zugeordnet sind. 
    
5. Ein Kommunikationsplan für betroffen Benutzer.
    
6. Ein Sicherungsplan für den Fall, dass die Upgrades fehlschlagen.
    
Alle Benutzer, die sich während des Upgrades im primären Pool befinden, können die Dienste erst verwenden, wenn das Upgrade abgeschlossen ist. Wenn Sie über einen funktionierenden sekundären Pool verfügen, können Sie die Auswirkungen auf Benutzer vermeiden, indem Sie sie vor dem Upgrade in den sekundären Pool verschieben. Verschieben Sie die Benutzer nach dem Upgrade wieder in den primären Pool.
  
### <a name="in-place-upgrade-methods"></a>In-Place-Upgrademethoden

Es gibt zwei Szenarien für In-Place Upgrade: 
  
- Die Move User-Methode, die keine Ausfallzeiten für Benutzer erfordert. 
    
- Die Offline-Methode, die Ausfallzeiten erfordert.
    
Es wird empfohlen, dass ein Upgrade der Offlinemethode während eines Wartungsfensters geplant wird und Benutzer über die Ausfallzeit benachrichtigt werden.
  
> [!NOTE]
> Beim Upgrade eines gekoppelten Pools auf Lync Server 2013 möchten Sie beide Pools auf Skype for Business Server 2015 aktualisieren. Achten Sie darauf, den zweiten Pool unmittelbar nach dem Upgrade des ersten Pools zu aktualisieren. Wenn in einem Pool Lync Server 2013 ausgeführt wird und im zweiten Pool Skype for Business Server 2015 ausgeführt wird, werden die Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool 2013 und der zweite 2015 ausgeführt wird und es zu einem Notfall kommt, kann es zu Datenverlusten kommen, da das Poolfailover im Notfallmodus nicht unterstützt wird, wenn gekoppelte Pools nicht die gleiche Version sind. 
  
#### <a name="in-place-upgrade-offline-method"></a>In-Place-Upgrade-Offlinemethode

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Benutzerpools verschieben möchten. Während des Upgrades können Benutzer keine Lync- oder Skype for Business-Dienste verwenden. 
  
Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
![Lync 2013 für Skype-Benutzer offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie über gekoppelte Pools verfügen, entkoppeln Sie sie nicht vor dem Upgrade. 
  
Sobald Sie mit dem Upgrade eines Serverpools beginnen, müssen Sie das Upgrade des gesamten Pools abschließen. Skype for Business Server unterstützt nicht, dass nur ein Teil des Pools aktualisiert wird. 
  
#### <a name="move-users-method-no-user-downtime"></a>Move Users-Methode (keine Benutzerausfallzeit)
<a name="bkmk_MoveUsersMethod"> </a>

Um diese Methode zu verwenden, verschieben Sie Benutzer in einen anderen Pool, bevor Sie mit dem Upgrade beginnen. Während des Upgrades können Benutzer Lync-Dienste verwenden. Nachdem sie in den aktualisierten Pool verschoben wurden, können sie Skype for Business verwenden. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
> [!IMPORTANT]
> Im Rahmen von Move Users müssen Sie auch die globalen Konferenzverzeichnissen migrieren, die dem primären Pool zugeordnet sind. PstN-Einwahlkonferenzen lösen ConferenceID weiterhin in den Pool auf, der aktualisiert wird, anstelle des gekoppelten Pools. Daher müssen Sie Konferenzverzeichnissen verschieben, wenn Sie weiterhin möchten, dass während des Upgrades auf im Pool geplante PSTN-Konferenzen zugegriffen werden kann. 
  
![Schwimmdiagramm, das zeigt, dass Benutzer in einen anderen Pool verschoben werden, bevor der Pool aktualisiert wird und nach dem Upgrade wieder in den Pool verschoben wird.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Verschieben von Benutzern für das Hardwareupgrade
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware die Serveranforderungen für [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)nicht erfüllt, richten Sie eine neue Skype for Business Server 2015-Umgebung ein, und verschieben Sie die Benutzer dort. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess für das Upgrade von Lync Server 2010. 
  
![Ein Schwimmspurdiagramm, das zeigt, wie Benutzer im primären Front-End-Pool von Lync Server zu Skype for Business Server 2015 und im Lync Server-Pool, der außer Betrieb gesetzt wird, verschoben werden.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Direkter Upgradevorgang

 Upgrade von Lync Server 2013 auf Skype for Business Server 2015 mithilfe der folgenden Schritte:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass alle Dienste, die aktualisiert werden sollen, in einem ausgeführten Zustand sind.
    
3. Aktualisieren und veröffentlichen Sie die Topologiedatei mithilfe des Topologie-Generators.
    
4. Beenden Sie alle Dienste auf allen Front-End-Servern.
    
5. Installieren Sie neue erforderliche Komponenten für Skype for Business Server.
    
6. Starten Sie auf jedem Front-End-Server das In-Place Upgrade.
    
7. Starten Sie nach Abschluss des Upgrades alle Dienste neu.
    
   - Starten Sie die Dienste für den Front-End-Pool mit dem Befehl Start-CsPool neu.
    
   - Verwenden Sie für Nicht-Front-End-Server Start-CSWindowsService.
    
> [!NOTE]
>  Wenn Sie die vorhandenen Archivierungs- und Überwachungsdatenbanken nicht aktualisieren möchten, entfernen Sie die Abhängigkeit, bevor Sie die Topologie aktualisieren. Wenn Sie neue Archivierungs- und Überwachungsdatenbanken erstellen möchten, können Sie während des Upgrades einen neuen SQL erstellen und dem Pool zuordnen. Die Schritte dazu finden Sie im Thema[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > Ein-Ort-Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. Um das Unterbrechen der Benutzerdienste zu vermeiden, verwenden Sie die [Move Users-Methode (keine](upgrade.md#bkmk_MoveUsersMethod) Benutzerausfallzeit), um upgrade.> Während des Upgradeprozesses wird das xds-Replikat im lokalen freigegebenen Ordner auf dem Datenträgerlaufwerk mit dem größten freien Speicherplatz platziert. Wenn dieser Datenträger später entfernt wird, können Probleme auftreten, z. B. wenn Dienste nicht gestartet werden.
  
### <a name="upgrade-order"></a>Upgradereihenfolge

Aktualisieren Sie die Topologie von innen nach außen. Aktualisieren Sie zuerst alle Pools, dann die Edgeserver und schließlich den Pool für den zentralen Verwaltungsspeicher (Central Management Store, CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie Kerberos-Konten neu zuweisen und das Kennwort nach Abschluss des In-Place zurücksetzen. Informationen dazu finden Sie unter [Einrichten der Kerberos-Authentifizierung](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung der Koexistenz mit Lync Server 2013 und Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie Lync Server 2013 oder Lync Server 2010 ausführen, sie können jedoch nicht alle drei in derselben Topologie verwenden.
  
Wenn Sie eine Koexistenz zwischen Lync Server 2010 und Lync Server 2013 haben, wird empfohlen, die gesamte Topologie auf Lync Server 2013 zu aktualisieren und dann mithilfe des In-Place-Upgrades auf Skype for Business Server 2015 zu aktualisieren. Weitere Informationen finden Sie unter [Migration from Lync Server 2010 to Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).
  
Wenn Ihre Topologie in erster Linie Lync Server 2010 ist, führen Sie ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 aus, bevor Sie die Topologie auf Skype for Business Server 2015 aktualisieren. In diesem Fall verlieren Sie den Vorteil des In-Place-Upgrades und verfügen über eine Koexistenztopologie zwischen Lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die Koexistenzunterstützung von Skype for Business Server 2015 mit Lync Server 2013 und Lync Server 2010.
  
![Ein Diagramm, das die Koexistenzunterstützung für Skype for Business Server 2015 mit Lync Server 2013 oder Lync Server 2010 zeigt.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch Appliance und Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 unterstützt kein In-Place-Upgrade einer Survivable Branch Appliance (SBA) oder eines Survivable Branch Servers (SBS).
  
Wir unterstützen jedoch die Koexistenz von Skype for Business Server-Rechenzentren mit Lync Server 2010 oder Lync Server 2013 SBA/SBS. 
  
Wenn Sie ein In-Place Upgrade eines Lync Server 2013-Front-End-Pools (FE) mit einer zugeordneten Zweigstelle planen, können Sie die vorhandenen Benutzer im Lync Server 2013-SBA/SBS be lassen. Während des Upgrades wechseln die SBA/SBS-Benutzer in den Ausfallsicherheitsmodus und kehren nach Abschluss des Upgrades wieder zur normalen Funktionalität zurück. Weitere Informationen zur Benutzererfahrung während des Ausfallsicherheitsmodus finden Sie unter Ausfallsicherheitsfeatures für Zweigstellenstandorte [in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features).
  
Beim Migrieren einer Lync Server 2010-Topologie zu Skype for Business Server 2015 muss der SBA/SBS der Topologie wie bei der Migration zu Lync Server 2013 erneut hinzugefügt werden. Die erforderlichen Schritte finden Sie unter [Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool).
  
Richten Sie für Koexistenztopologien von Lync Server 2010 und Lync Server 2013 zunächst die Empfehlungen aus dem Abschnitt "Unterstützung für die Koexistenz mit Lync Server 2013 und Lync Server 2010" aus.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Umgebungsanforderungen für Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)