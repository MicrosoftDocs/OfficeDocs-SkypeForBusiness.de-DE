---
title: Planen des Upgrades auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: 'Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie berücksichtigen sollten, wenn Sie ein Upgrade auf Skype for Business Server 2015 planen.'
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860596"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen des Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie berücksichtigen sollten, wenn Sie ein Upgrade auf Skype for Business Server 2015 planen.
  
Verwenden Sie im Rahmen Ihres Plans zum Upgrade auf Skype for Business Server 2015 dieses Thema, um die empfohlenen Upgradepfade für Skype for Business Server 2015 zu verstehen, wie das In-Place Upgrade funktioniert, welche Koexistenzszenarien unterstützt werden und wie der Upgradeprozess aussieht.

> [!NOTE]
> Direkte Upgrades waren in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Parallele Koexistenz wird unterstützt. Weitere Informationen finden Sie unter [Migration zu Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md).
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Upgradepfade für Skype for Business Server 2015

 Verwenden Sie zum Upgrade von Lync Server 2013, Lync Server 2010 oder Office Communications Server 2007 R2 auf Skype for Business Server 2015 die folgenden Upgradepfade:
  
> [!CAUTION]
> In-Place Upgrade verschiebt automatisch Konferenzverzeichnisse von Lync Server 2013 auf Skype for Business Server 2015. Wenn Sie jedoch planen, Konferenzverzeichnisse manuell zu verschieben, ist es sehr wichtig, die Skype for Business Server 2015-Verwaltungsshell zu verwenden. Wenn Sie versuchen, die Lync Server 2013-Verwaltungsshell zum Verschieben von Konferenzverzeichnissen von Lync Server 2013 in Skype for Business Server 2015 zu verwenden, kann ein Datenverlust auftreten. Im Allgemeinen sollten Sie, wenn Sie mit Skype for Business Server 2015 in beliebiger Kapazität arbeiten, den Toolsatz Skype for Business Server 2015 verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Verwenden Sie zum Upgrade den Skype for Business Server Topologie-Generator und das neue Feature In-Place Upgrade auf jedem server, der dem Pool zugeordnet ist. Ausführliche Schritte finden Sie unter [Plan to upgrade from Lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). <br/> |
|Lync Server 2010 + Lync Server 2013 (dualer Modus)  <br/> |Führen Sie zuerst ein Upgrade auf Lync Server 2013 durch, und führen Sie dann ein Upgrade auf Skype for Business Server 2015 mithilfe des neuen In-Place-Upgradefeatures durch. Wenn ihre Topologie jedoch primär Lync Server 2010 ist, können Sie auch ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durchführen und dann direkt auf Skype for Business Server 2015 aktualisieren. In diesem Fall können Sie In-Place Upgrade nicht nutzen und würden eine direkte Koexistenz zwischen Lync Server 2010 und Skype for Business Server 2015 verwenden. Triexistenz wird nicht unterstützt, aber Koexistenz wird unterstützt.  <br/> |
|Lync Server 2010  <br/> |Rufen Sie einen neuen Skype for Business Server 2015-Pool auf, und migrieren Sie dann Benutzer zu diesem neuen Pool. Anschließend können Sie den alten Lync Server 2010-Pool außer Betrieb lassen. Das Upgrade von Lync Server 2010 auf Skype for Business Server 2015 ähnelt dem Upgrade von Lync Server 2010 auf Lync Server 2013. Siehe [Migration von Lync Server 2010 zu Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie eine von zwei Optionen aus: <br/>  Richten Sie eine neue Skype for Business Server 2015-Umgebung ein. <br/>  Oder wenn Ihre Hardware und Software die Anforderungen für Skype for Business Server 2015 erfüllen, führen Sie ein Upgrade auf Lync Server 2013 durch, und führen Sie dann ein Upgrade auf Skype for Business Server 2015 durch, indem Sie das neue Feature In-Place Upgrade verwenden. Weitere Informationen finden Sie unter [Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) und [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird in Skype for Business Server 2015 unterstützt, in Lync Server 2013 jedoch nicht. Wenn Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen möchten, muss der Pool zuerst auf Skype for Business Server 2015 aktualisiert werden, indem Sie die In-Place Upgrade-Methode verwenden, wie in diesem Dokument beschrieben. Anschließend können Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen. Weitere Informationen finden Sie unter ["Upgrade auf SQL Server 2014](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014)". Weitere Informationen zu den Datenbankanforderungen finden Sie unter [Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planen des Upgrades von Lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Lync Server 2013-Systeme mit dem neuen Feature In-Place Upgrade auf Skype for Business Server 2015 aktualisieren. Das direkte Upgrade bietet eine Lösung mit einem Klick, die Zertifikate sichert, Serverkomponenten deinstalliert, lokale Datenbanken aktualisiert und die Rollen Skype for Business Server 2015 installiert. Bei einem direkten Upgrade sollen vorhandene Hardware- und Serverinvestitionen erhalten bleiben, wodurch die Gesamtkosten für die Bereitstellung Skype for Business Server 2015 reduziert werden.
  
> [!NOTE]
> In-Place Upgrade ermöglicht ihnen die Verwendung der gleichen Hardware beim Upgrade auf Skype for Business Server. Die Wiederverwendung der gleichen Hardware führt jedoch nicht zu derselben Leistungskapazität. Sie sollten nicht erwarten, dass die Leistungslasten für Lync Server 2013 und Skype for Business Server 2015 identisch sind. 
  
> [!NOTE]
> In-Place Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. 
  
Bei einem direkten Upgrade wird der Lync Server 2013-Pool offline geschaltet und auf einen Skype for Business Server 2015-Pool aktualisiert. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines In-Place Upgradeplans

Erstellen Sie einen Plan, der Folgendes umfasst:
  
1. Ein Verständnis Ihrer aktuellen Topologie.
    
    > [!NOTE]
    > Deinstallieren Sie unbedingt das LRS Admin-Tool für Lync Server 2013, bevor Sie In-Place Upgrade ausführen. Das LRS Admin Tool für Lync Server 2013 kann nicht mit Skype for Business Server 2015 koexistieren. Nachdem Sie In-Place Upgrade ausgeführt haben, installieren Sie das neue LRS-Admin-Tool. Weitere Informationen finden Sie im [Microsoft Lync Room System Administrative Web Portal für Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807).
  
2. Der primäre Pool für das Upgrade.
    
3. Unabhängig davon, ob Sie ein Upgrade der Archivierungs- und Überwachungsdatenbanken durchführen oder neue Datenbanken erstellen.
    
4. Die In-Place Upgrademethode, die Sie verwenden: Offline oder Verschieben von Benutzern. Als Teil von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnisse migrieren, die dem primären Pool zugeordnet sind. 
    
5. Ein Kommunikationsplan für betroffene Benutzer.
    
6. Ein Sicherungsplan für den Fall, dass die Upgrades fehlschlagen.
    
Benutzer, die sich im primären Pool befinden, während das Upgrade ausgeführt wird, können die Dienste erst nach Abschluss des Upgrades verwenden. Wenn Sie über einen funktionierenden sekundären Pool verfügen, können Sie Auswirkungen auf Benutzer vermeiden, indem Sie sie vor dem Upgrade in den sekundären Pool verschieben. Verschieben Sie die Benutzer nach dem Upgrade wieder in den primären Pool.
  
### <a name="in-place-upgrade-methods"></a>Direkte Upgrademethoden

Es gibt zwei Szenarien für In-Place Upgrade: 
  
- Die Move User-Methode, die keine Ausfallzeiten für Benutzer erfordert. 
    
- Die Offlinemethode, die Ausfallzeiten erfordert.
    
Es wird empfohlen, ein Offlinemethodenupgrade während eines Wartungsfensters zu planen, und die Benutzer werden über die Ausfallzeiten benachrichtigt.
  
> [!NOTE]
> Wenn Sie einen gekoppelten Pool auf Lync Server 2013 aktualisieren und beide Pools auf Skype for Business Server 2015 aktualisieren möchten. Stellen Sie sicher, dass sie den zweiten Pool unmittelbar nach dem Upgrade des ersten Pools aktualisieren. Wenn in einem Pool Lync Server 2013 ausgeführt wird und der zweite Pool Skype for Business Server 2015 ausgeführt wird, werden die Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool 2013 ausführt und der zweite 2015 ist und ein Notfall vorliegt, können Daten verloren gehen, da poolfailover im Notfallmodus nicht unterstützt wird, wenn gekoppelte Pools nicht dieselbe Version aufweisen. 
  
#### <a name="in-place-upgrade-offline-method"></a>Offline-Methode für direktes Upgrade

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Benutzerpools verschieben möchten. Während des Upgrades können Benutzer Lync oder Skype for Business Dienste nicht verwenden. 
  
Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
![Lync 2013 Zum Skype von Benutzern offline.](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie über gekoppelte Pools verfügen, sollten Sie diese vor dem Upgrade nicht entkoppeln. 
  
Sobald Sie mit dem Upgrade eines Serverpools beginnen, müssen Sie das Upgrade des gesamten Pools abschließen. Skype for Business Server unterstützt nicht, dass nur ein Teil des Pools aktualisiert wird. 
  
#### <a name="move-users-method-no-user-downtime"></a>Move Users-Methode (keine Benutzerausfallzeit)
<a name="bkmk_MoveUsersMethod"> </a>

Um diese Methode zu verwenden, verschieben Sie Benutzer in einen anderen Pool, bevor Sie das Upgrade starten. Während des Upgrades können Benutzer Lync-Dienste verwenden. Nachdem sie in den aktualisierten Pool verschoben wurden, können sie Skype for Business verwenden. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
> [!IMPORTANT]
> Als Teil von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnisse migrieren, die dem primären Pool zugeordnet sind. Bei PSTN-Einwahlkonferenzen wird conferenceID weiterhin in den Pool aufgelöst, für den ein Upgrade ausgeführt wird, anstelle des gekoppelten Pools. Sie müssen also Konferenzverzeichnisse verschieben, wenn Sie weiterhin möchten, dass PSTN-Konferenzen, die im Pool geplant sind, während des Upgrades zugänglich sind. 
  
![Schwimmdiagramm, das zeigt, dass Benutzer in einen anderen Pool verschoben werden, bevor der Pool aktualisiert und nach dem Upgrade wieder in den Pool verschoben wird.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Verschieben von Benutzern für das Hardwareupgrade
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware die [Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) nicht erfüllt, richten Sie eine neue Skype for Business Server 2015-Umgebung ein, und verschieben Sie die Benutzer dorthin. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess für das Upgrade von Lync Server 2010. 
  
![Diagramm der Schwimmspur, das Zeigt, dass Benutzer im primären Front-End-Pool von Lync Server in Skype for Business Server 2015 verschoben werden und der Lync Server-Pool außer Betrieb genommen wird.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Direkter Upgradevorgang

 Führen Sie die folgenden Schritte aus, um ein Upgrade von Lync Server 2013 auf Skype for Business Server 2015 auszuführen:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass alle Dienste, für die ein Upgrade ausgeführt werden soll, ausgeführt werden.
    
3. Aktualisieren und veröffentlichen Sie die Topologiedatei mithilfe des Topologie-Generators.
    
4. Beenden Sie alle Dienste auf allen Front-End-Servern.
    
5. Installieren Sie die neuen erforderlichen Komponenten, die für Skype for Business Server erforderlich sind.
    
6. Starten Sie auf jedem Front-End-Server das In-Place Upgrade.
    
7. Starten Sie nach Abschluss des Upgrades alle Dienste neu.
    
   - Starten Sie für den Front-End-Pool die Dienste mithilfe des Befehls "Start-CsPool" neu.
    
   - Verwenden Sie für Nicht-Front-End-Server Start-CSWindowsService.
    
> [!NOTE]
>  Wenn Sie ihre vorhandenen Archivierungs- und Überwachungsdatenbanken nicht aktualisieren möchten, entfernen Sie die Abhängigkeit, bevor Sie die Topologie aktualisieren. Wenn Sie während des Upgrades neue Archivierungs- und Überwachungsdatenbanken erstellen möchten, können Sie einen neuen SQL Speichern erstellen und dem Pool zuordnen. Die Dazu erforderlichen Schritte finden Sie unter "[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)". > Direktes Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. Um eine Unterbrechung der Dienste von Benutzern zu vermeiden, verwenden [Sie die Methode "Benutzer verschieben" (keine Benutzerausfallzeit)](upgrade.md#bkmk_MoveUsersMethod) zum Upgrade.> Während des Upgradeprozesses wird das xds-Replikat im lokalen freigegebenen Ordner auf dem Laufwerk mit dem meisten freien Speicherplatz abgelegt. Wenn dieser Datenträger später entfernt wird, können Probleme auftreten, z. B. dienste, die nicht gestartet werden.
  
### <a name="upgrade-order"></a>Upgradeauftrag

Aktualisieren Sie die Topologie von innen nach außen. Führen Sie zuerst ein Upgrade aller Pools, dann der Edgeserver und schließlich des CMS-Pools (Central Management Store) durch. 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie Kerberos-Konten neu zuweisen und das Kennwort zurücksetzen, nachdem das In-Place Upgrade abgeschlossen ist. Informationen dazu finden Sie unter [Einrichten der Kerberos-Authentifizierung](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung für koexistenz mit Lync Server 2013 und Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie Lync Server 2013 oder Lync Server 2010 ausführen, aber nicht alle drei in derselben Topologie.
  
Wenn zwischen Lync Server 2010 und Lync Server 2013 eine Koexistenz besteht, wird empfohlen, die gesamte Topologie auf Lync Server 2013 zu aktualisieren und dann mit dem In-Place-Upgrade auf Skype for Business Server 2015 zu aktualisieren. Weitere Informationen finden Sie unter [Migration von Lync Server 2010 zu Lync Server 2013](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013).
  
Wenn ihre Topologie in erster Linie Lync Server 2010 ist, führen Sie ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durch, bevor Sie die Topologie auf Skype for Business Server 2015 aktualisieren. In diesem Fall verlieren Sie den Vorteil des In-Place-Upgrades und verfügen über eine Koexistenztopologie zwischen Lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die Koexistenzunterstützung von Skype for Business Server 2015 mit Lync Server 2013 und Lync Server 2010.
  
![Ein Diagramm, das die Koexistenzunterstützung für Skype for Business Server 2015 mit Lync Server 2013 oder Lync Server 2010 zeigt.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch Appliance und vorhandenem Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 unterstützt kein In-Place Upgrade einer Survivable Branch Appliance (SBA) oder eines Survivable Branch Server (SBS).
  
Wir unterstützen jedoch die Koexistenz von Skype for Business Server Rechenzentren mit Lync Server 2010 oder Lync Server 2013 SBA/SBS. 
  
Bei der Planung eines In-Place Upgrades eines Lync Server 2013-Front-End-Pools (FE) mit einer zugeordneten Verzweigung können Sie die vorhandenen Benutzer im Lync Server 2013 SBA/SBS belassen. Während des Upgrades wechseln die SBA/SBS-Benutzer in den Resilienzmodus und kehren nach Abschluss des Upgrades wieder zur normalen Funktionalität zurück. Weitere Informationen zur Benutzererfahrung während des Ausfallsicherheitsmodus finden Sie [unter den Ausfallsicherheitsfeatures für Zweigstellenstandorte in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features).
  
Bei der Migration einer Lync Server 2010-Topologie zu Skype for Business Server 2015 muss der SBA/SBS der Topologie hinzugefügt werden, ähnlich der Migration zu Lync Server 2013. Die erforderlichen Schritte finden Sie unter [Verbinden der Survivable Branch Appliance mit dem Lync Server 2013-Front-End-Pool](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool).
  
Richten Sie für Koexistenztopologien von Lync Server 2010 und Lync Server 2013 zuerst die Empfehlungen aus dem Abschnitt "Unterstützung für Koexistenz mit Lync Server 2013 und Lync Server 2010" aus.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Umweltanforderungen für Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
