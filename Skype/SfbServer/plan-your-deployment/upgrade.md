---
title: Planen des Upgrades auf Skype for Business Server 2015
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: 69b1d9df20330ad0baecbc1c5abe59e76808185a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831975"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen des Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: Erfahren Sie mehr über die Dinge, die Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine kostenlose Testversion von Skype for Business Server 2015 aus dem Microsoft Evaluation Center unter: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) herunter.
  
Verwenden Sie dieses Thema im Rahmen Ihres Plans für das Upgrade auf Skype for Business Server 2015, um die empfohlenen Upgradepfade für Skype for Business Server 2015, die Funktionsweise des In-Place-Upgrades, die unterstützten Koexistenzszenarien und den Upgradeprozess zu verstehen.

> [!NOTE]
> In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die nebeneinander ausgeführte Koexistenz wird unterstützt. Weitere Informationen finden Sie unter ["Migration zu Skype for Business Server 2019".](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Upgradepfade auf Skype for Business Server 2015

 Zum Upgrade von Lync Server 2013, Lync Server 2010 oder Office Communications Server 2007 R2 auf Skype for Business Server 2015 verwenden Sie die folgenden Upgradepfade:
  
> [!CAUTION]
> In-Place upgrade automatically moves conference directories from Lync Server 2013 to Skype for Business Server 2015. Wenn Sie jedoch planen, Konferenzverzeichnissen manuell zu verschieben, ist es sehr wichtig, die Skype for Business Server 2015-Verwaltungsshell zu verwenden. Wenn Sie versuchen, die Lync Server 2013-Verwaltungsshell zum Verschieben von Konferenzverzeichnissen von Lync Server 2013 zu Skype for Business Server 2015 zu verwenden, kann es zu Datenverlusten kommen. Wenn Sie mit Skype for Business Server 2015 in beliebiger Kapazität arbeiten, sollten Sie im Allgemeinen den Skype for Business Server 2015-Toolsatz verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Verwenden Sie zum Upgrade den Skype for Business Server-Topologie-Generator und die neue In-Place-Upgrade-Funktion auf jedem server, der dem Pool zugeordnet ist. Ausführliche Schritte finden Sie unter "Planen des Upgrades von [Lync Server 2013 auf Skype for Business Server 2015"](upgrade.md#BKMK_PlanUpgradeFromLync2013) und ["Upgrade auf Skype for Business Server 2015".](../deploy/upgrade-to-skype-for-business-server.md) <br/> |
|Lync Server 2010 + Lync Server 2013 (dualer Modus)  <br/> |Führen Sie zunächst ein Upgrade auf Lync Server 2013 und dann ein Upgrade auf Skype for Business Server 2015 mithilfe des neuen Features In-Place Upgrade durch. Wenn Ihre Topologie jedoch primär für Lync Server 2010 ist, können Sie auch ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durchführen und dann direkt auf Skype for Business Server 2015 aktualisieren. In diesem Fall können Sie das In-Place-Upgrade nicht nutzen und würden eine gerade Koexistenz zwischen Lync Server 2010 und Skype for Business Server 2015 verwenden. Triexistenz wird nicht unterstützt, Koexistenz wird jedoch unterstützt.  <br/> |
|Lync Server 2010  <br/> |Starten Sie einen neuen Skype for Business Server 2015-Pool, und migrieren Sie die Benutzer zu diesem neuen Pool. Anschließend können Sie den alten Lync Server 2010-Pool außer Betrieb lassen. Das Upgrade von Lync Server 2010 auf Skype for Business Server 2015 ähnelt dem Upgrade von Lync Server 2010 auf Lync Server 2013. Siehe [Migration von Lync Server 2010 zu Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie eine von zwei Optionen aus: <br/>  Richten Sie eine neue Skype for Business Server 2015-Umgebung ein. <br/>  Oder wenn Ihre Hardware und Software die Anforderungen für Skype for Business Server 2015 erfüllt, führen Sie ein Upgrade auf Lync Server 2013 und dann ein Upgrade auf Skype for Business Server 2015 mithilfe der neuen In-Place-Upgradefunktion durch. Weitere Informationen finden Sie unter Serveranforderungen für [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) und Migration von Office Communications Server [2007 R2 zu Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird in Skype for Business Server 2015 unterstützt, in Lync Server 2013 jedoch nicht. Wenn Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen möchten, muss der Pool zuerst mithilfe der In-Place-Upgrade-Methode auf Skype for Business Server 2015 aktualisiert werden, wie in diesem Dokument beschrieben. Sie können dann ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen. Weitere Informationen finden Sie unter [Upgrade auf SQL Server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Weitere Informationen zu Datenbankanforderungen finden Sie unter [Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planen des Upgrades von Lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Lync Server 2013-Systeme mithilfe der neuen Funktion In-Place Upgrade auf Skype for Business Server 2015 aktualisieren. Das in-Place-Upgrade bietet eine Lösung mit nur einem Klick, die Zertifikate, Serverkomponenten deinstalliert, lokale Datenbanken aktualisiert und die Skype for Business Server 2015-Rollen installiert. Durch ein in-Place-Upgrade werden vorhandene Hardware- und Serverinvestitionen beibehalten, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 reduziert werden.
  
> [!NOTE]
> In-Place Upgrade ermöglicht Ihnen die Verwendung derselben Hardware beim Upgrade auf Skype for Business Server. Die Erneutverschleierung derselben Hardware führt jedoch nicht zu derselben Leistungsfähigkeit. Sie sollten nicht erwarten, dass die Leistungslasten für Lync Server 2013 und Skype for Business Server 2015 identisch sind. 
  
> [!NOTE]
> In-Place upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. 
  
Bei einem in-Place-Upgrade wird der Lync Server 2013-Pool offline geschaltet und auf einen Skype for Business Server 2015-Pool aktualisiert. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines In-Place Upgradeplans

Erstellen Sie einen Plan, der:
  
1. Ein Verständnis Ihrer aktuellen Topologie.
    
    > [!NOTE]
    > Deinstallieren Sie unbedingt das LRS Admin Tool für Lync Server 2013, bevor Sie In-Place ausführen. Das LRS Admin Tool für Lync Server 2013 kann nicht zusammen mit Skype for Business Server 2015 verwendet werden. Installieren Sie nach In-Place Upgrade das neue LRS-Verwaltungstool. Weitere Informationen finden Sie im Webportal zur Verwaltung [von Microsoft Lync Room System für Skype for Business Server 2015.](https://go.microsoft.com/fwlink/?LinkID=544807)
  
2. Der primäre Pool für das Upgrade.
    
3. Unabhängig davon, ob Sie die Archivierungs- und Überwachungsdatenbanken aktualisieren oder neue erstellen.
    
4. The In-Place Upgrade method you'll use: Offline or Move Users. Im Rahmen von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnissen migrieren, die dem primären Pool zugeordnet sind. 
    
5. Ein Kommunikationsplan für die betroffen benutzer.
    
6. Ein Sicherungsplan für den Fall, dass die Upgrades fehlschlagen.
    
Alle Benutzer, die sich während des Upgrades im primären Pool befinden, können die Dienste erst verwenden, wenn das Upgrade abgeschlossen ist. Wenn Sie über einen funktionierenden sekundären Pool verfügen, können Sie die Auswirkungen auf die Benutzer vermeiden, indem Sie sie vor dem Upgrade in den sekundären Pool verschieben. Verschieben Sie die Benutzer nach dem Upgrade zurück in den primären Pool.
  
### <a name="in-place-upgrade-methods"></a>In-Place-Upgrademethoden

Es gibt zwei Szenarien für In-Place Upgrade: 
  
- Die Methode "Move User", die keine Downtime für Benutzer erfordert. 
    
- Die Offlinemethode, die Ausfallzeiten erfordert.
    
Es wird empfohlen, ein Offlinemethodesupgrade während eines Wartungsfensters zu terminieren, und die Benutzer werden über die Ausfallzeit benachrichtigt.
  
> [!NOTE]
> Beim Upgrade eines Poolpaars auf Lync Server 2013 möchten Sie beide Pools auf Skype for Business Server 2015 aktualisieren. Stellen Sie sicher, dass Sie den zweiten Pool unmittelbar nach dem Upgrade des ersten Pools aktualisieren. Wenn in einem Pool Lync Server 2013 und im zweiten Pool Skype for Business Server 2015 ausgeführt wird, werden die Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool 2013 und der zweite 2015 ausgeführt wird und es zu einem Notfall kommt, kann es zu Datenverlusten kommen, da das Poolfailover im Notfallmodus nicht unterstützt wird, wenn gepaarte Pools nicht dieselbe Version sind. 
  
#### <a name="in-place-upgrade-offline-method"></a>Offlinemethode für das in-place-Upgrade

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Benutzerpools verschieben möchten. Während des Upgrades können Benutzer keine Lync- oder Skype for Business-Dienste verwenden. 
  
Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
![Lync 2013-zu-Skype-Benutzer offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie über gepaarte Pools verfügen, entkoppeln Sie diese nicht vor dem Upgrade. 
  
Sobald Sie mit dem Upgrade eines Serverpools beginnen, müssen Sie das Upgrade des gesamten Pools abschließen. Skype for Business Server unterstützt nicht, nur einen Teil des Pools zu upgraden. 
  
#### <a name="move-users-method-no-user-downtime"></a>Methode zum Verschieben von Benutzern (keine Benutzerausfallzeit)
<a name="bkmk_MoveUsersMethod"> </a>

Um diese Methode zu verwenden, verschieben Sie Benutzer in einen anderen Pool, bevor Sie mit dem Upgrade beginnen. Während des Upgrades können Benutzer die Lync-Dienste verwenden. Nachdem sie in den aktualisierten Pool verschoben wurden, können sie Skype for Business verwenden. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
> [!IMPORTANT]
> Im Rahmen von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnissen migrieren, die dem primären Pool zugeordnet sind. PstN-Einwahlkonferenzen lösen conferenceID weiterhin in den Pool auf, der aktualisiert wird, statt in den gekoppelten Pool. Daher müssen Sie Konferenzverzeichnissen verschieben, wenn während des Upgrades weiterhin auf im Pool geplante PSTN-Konferenzen zugegriffen werden kann. 
  
![Ein Diagramm mit einem Diagramm, das zeigt, wie Benutzer vor dem Upgrade des Pools in einen anderen Pool verschoben werden und nach dem Upgrade wieder in den Pool verschoben werden.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Verschieben von Benutzern für ein Hardwareupgrade
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware die Serveranforderungen für [Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)nicht erfüllt, richten Sie eine neue Skype for Business Server 2015-Umgebung ein, und verschieben Sie die Benutzer dort. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess für das Upgrade von Lync Server 2010. 
  
![Diagramm mit einer 12-Stunden-Schaltung, die zeigt, wie Benutzer im primären Front-End-Pool von Lync Server zu Skype for Business Server 2015 verschoben werden, und im Lync Server-Pool, der außer Betrieb genommen wird.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Direkter Upgradevorgang

 Upgrade von Lync Server 2013 auf Skype for Business Server 2015 mithilfe der folgenden Schritte:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass sich alle Dienste, die aktualisiert werden sollen, in einem ausgeführten Zustand befinden.
    
3. Aktualisieren und veröffentlichen Sie die Topologiedatei mithilfe des Topologie-Generators.
    
4. Beenden Sie alle Dienste auf allen Front-End-Servern.
    
5. Installieren Sie neue erforderliche Komponenten für Skype for Business Server.
    
6. Starten Sie auf jedem Front-End-Server das In-Place Upgrade.
    
7. Starten Sie nach Abschluss des Upgrades alle Dienste neu.
    
   - Starten Sie die Dienste für den Front-End-Pool mit dem Befehl "Start-CsPool" neu.
    
   - Verwenden Sie start-CSWindowsService für Nicht-Front-End-Server.
    
> [!NOTE]
>  Wenn Sie ihre vorhandenen Archivierungs- und Überwachungsdatenbanken nicht aktualisieren möchten, entfernen Sie die Abhängigkeit, bevor Sie die Topologie aktualisieren. Wenn Sie neue Archivierungs- und Überwachungsdatenbanken erstellen möchten, können Sie während des Upgrades einen neuen SQL erstellen und dem Pool zuordnen. Die Schritte dazu finden Sie im Thema["Upgrade auf Skype for Business Server 2015".](../deploy/upgrade-to-skype-for-business-server.md) > A0 unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. Um zu verhindern, dass die Dienste der Benutzer unterbrochen werden, verwenden Sie die Methode zum Verschieben von Benutzern [(keine](upgrade.md#bkmk_MoveUsersMethod) Benutzerausfallzeit) zum Upgrade.> Während des Upgradeprozesses wird das xds-Replikat im lokalen freigegebenen Ordner auf dem Festplattenlaufwerk mit dem meisten freien Speicherplatz platziert. Wenn dieser Datenträger später entfernt wird, können Probleme auftreten, z. B. dass Dienste nicht gestartet werden.
  
### <a name="upgrade-order"></a>Upgradereihenfolge

Aktualisieren Sie die Topologie von innen nach außen. Aktualisieren Sie zuerst alle Pools, dann die Edgeserver und schließlich den Zentralen Verwaltungsspeicher (CMS)-Pool. 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie die Kerberos-Konten neu zuweisen und das Kennwort nach Abschluss des In-Place zurücksetzen. Informationen dazu finden Sie unter [Einrichten der Kerberos-Authentifizierung.](https://go.microsoft.com/fwlink/p/?LinkId=530342)
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung für koexistenz mit Lync Server 2013 und Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie Lync Server 2013 oder Lync Server 2010 ausführen, sie können jedoch nicht alle drei in derselben Topologie verwenden.
  
Wenn Sie über eine Koexistenz zwischen Lync Server 2010 und Lync Server 2013 verfügen, wird empfohlen, die gesamte Topologie auf Lync Server 2013 und dann mithilfe des In-Place-Upgrades auf Skype for Business Server 2015 zu aktualisieren. Weitere Informationen finden Sie unter [Migration from Lync Server 2010 to Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Wenn Ihre Topologie in erster Linie Lync Server 2010 ist, führen Sie ein Rollback der Lync Server 2013-Komponenten auf Lync Server 2010 durch, bevor Sie die Topologie auf Skype for Business Server 2015 aktualisieren. In diesem Fall verlieren Sie den Vorteil des In-Place-Upgrades und verfügen über eine Koexistenztopologie zwischen Lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die Koexistenzunterstützung von Skype for Business Server 2015 mit Lync Server 2013 und Lync Server 2010.
  
![Ein Diagramm, das die Unterstützung der Koexistenz von Skype for Business Server 2015 mit Lync Server 2013 oder Lync Server 2010 zeigt.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch Appliance und einem vorhandenen Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 unterstützt kein In-Place Upgrade einer Survivable Branch Appliance (SBA) oder eines Survivable Branch Servers (SBS).
  
Wir unterstützen jedoch die Koexistenz von Skype for Business Server-Rechenzentren mit Lync Server 2010 oder Lync Server 2013 SBA/SBS. 
  
Bei der Planung eines In-Place-Upgrades eines Lync Server 2013-Front-End-Pools (FE)-Pools mit einer zugeordneten Verzweigung können Sie die vorhandenen Benutzer im Lync Server 2013-SBA/SBS be lassen. Während des Upgrades wechseln die SBA/SBS-Benutzer in den Ausfallsicherheitsmodus und kehren nach Abschluss des Upgrades wieder zur normalen Funktionalität zurück. Weitere Informationen zur Benutzererfahrung während des Ausfallsicherheitsmodus finden Sie unter "Ausfallsicherheitsfunktionen für Zweigstellenstandorte" [in Lync Server 2013.](https://technet.microsoft.com/library/gg398715.aspx)
  
Bei der Migration einer Lync Server 2010-Topologie zu Skype for Business Server 2015 muss der SBA/SBS der Topologie wie bei der Migration zu Lync Server 2013 erneut hinzugefügt werden. Die erforderlichen Schritte finden Sie unter "Verbinden der [Survivable Branch Appliance mit dem Lync Server 2013-Front-End-Pool".](https://technet.microsoft.com/library/jj688026.aspx)
  
Richten Sie für Koexistenztopologien von Lync Server 2010 und Lync Server 2013 zunächst die Empfehlungen aus dem Abschnitt "Unterstützung der Koexistenz mit Lync Server 2013 und Lync Server 2010" aus.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Umgebungsanforderungen für Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Serveranforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
