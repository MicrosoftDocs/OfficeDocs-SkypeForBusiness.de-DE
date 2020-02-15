---
title: Planen des Upgrades auf Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: Hier erfahren Sie, was Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030639"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Planen des Upgrades auf Skype for Business Server 2015
 
Zusammenfassung: Hier erfahren Sie, was Sie bei der Planung eines Upgrades auf Skype for Business Server 2015 berücksichtigen sollten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server 2015 vom Microsoft Evaluation Center [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)unter: herunter.
  
Im Rahmen Ihres Plans für ein Upgrade auf Skype for Business Server 2015 verwenden Sie dieses Thema, um die empfohlenen Upgrade-Pfade für Skype for Business Server 2015, die Funktionsweise des in-Place-Upgrades, die unterstützten Koexistenz-Szenarien und den Verlauf des Upgrades zu verstehen. sieht aus wie.

> [!NOTE]
> In-Place-Upgrades waren in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Nebeneinander nebeneinander unterstützt wird, finden Sie unter [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) Weitere Informationen.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Empfohlene Upgrade-Pfade zu Skype for Business Server 2015

 Wenn Sie ein Upgrade von lync Server 2013, lync Server 2010 oder Office Communications Server 2007 R2 auf Skype for Business Server 2015 durchführen möchten, verwenden Sie die folgenden Upgrade-Pfade:
  
> [!CAUTION]
> Durch ein direktes Upgrade werden die Konferenzverzeichnisse automatisch von lync Server 2013 in Skype for Business Server 2015 verschoben. Wenn Sie jedoch das manuelle Migrieren von Konferenz Verzeichnissen planen, ist es sehr wichtig, dass Sie die Skype for Business Server 2015-Verwaltungsshell verwenden. Wenn Sie versuchen, die lync Server 2013-Verwaltungsshell zum Migrieren von Konferenz Verzeichnissen von lync Server 2013 in Skype for Business Server 2015 zu verwenden, kann es zu Datenverlust kommen. Im Allgemeinen sollten Sie, wenn Sie mit Skype for Business Server 2015 in einer beliebigen Kapazität arbeiten, das Skype for Business Server 2015-Tool-Setup verwenden.  
  
|**Version**|**Empfehlungen**|
|:-----|:-----|
|Lync Server 2013  <br/> | Um ein Upgrade durchführen zu können, verwenden Sie den Skype for Business Server Topologie-Generator und das Feature für die neue in-Place-Aktualisierung auf jedem Server, der dem Pool zugeordnet ist. Ausführliche Schritte finden Sie unter [Plan to upgrade from lync Server 2013 to Skype for Business Server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) and [Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) . <br/> |
|Lync Server 2010 + lync Server 2013 (dualer Modus)  <br/> |Führen Sie zunächst ein Upgrade auf lync Server 2013 durch, und aktualisieren Sie dann mithilfe der neuen Funktion für ein direktes Upgrade auf Skype for Business Server 2015. Wenn Ihre Topologie jedoch primär ist lync Server 2010 können Sie auch die lync Server 2013 Komponenten auf lync Server 2010 zurücksetzen und dann direkt auf Skype for Business Server 2015 aktualisieren. In diesem Fall können Sie das direkte Upgrade nicht nutzen und würden ein Heterosexuelles nebeneinander zwischen lync Server 2010 und Skype for Business Server 2015 verwenden. Tri-Existenz wird nicht unterstützt, aber Koexistenz wird unterstützt.  <br/> |
|Lync Server 2010  <br/> |Rufen Sie einen neuen Skype for Business Server 2015 Pool auf, und migrieren Sie dann Benutzer zu diesem neuen Pool. Anschließend können Sie den alten lync Server 2010 Pool außer Betrieb nehmen. Das Upgrade von lync Server 2010 auf Skype for Business Server 2015 ähnelt dem Upgrade von lync Server 2010 auf lync Server 2013. Weitere Informationen finden Sie unter [Migration from lync Server 2010 to lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Wählen Sie eine von zwei Optionen aus: <br/>  Richten Sie eine neue Skype for Business Server 2015 Umgebung ein. <br/>  Oder wenn Ihre Hardware und Ihre Software die Anforderungen für Skype for Business Server 2015 erfüllen, ein Upgrade auf lync Server 2013 durchführen und dann mithilfe der neuen Funktion für ein direktes Upgrade auf Skype for Business Server 2015 aktualisieren. Weitere Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md) und [Migration von Office Communications Server 2007 R2 zu lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 wird in Skype for Business Server 2015 unterstützt, wird jedoch in lync Server 2013 nicht unterstützt. Wenn Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen möchten, muss der Pool zuerst mithilfe der in-Place-Upgrade-Methode, wie in diesem Dokument beschrieben, auf Skype for Business Server 2015 aktualisiert werden. Anschließend können Sie ein Upgrade von SQL Server 2012 auf SQL Server 2014 durchführen, siehe [Upgrade auf SQL Server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Weitere Informationen zu den Datenbankanforderungen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Planen des Upgrades von lync Server 2013 auf Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können lync Server 2013 Systeme auf Skype for Business Server 2015 mithilfe der neuen Funktion für ein direktes Upgrade aktualisieren. Ein direktes Upgrade bietet eine Lösung mit einem Mausklick, die Zertifikate sichert, Server Komponenten deinstalliert, lokale Datenbanken aktualisiert und die Skype for Business Server 2015 Rollen installiert. Das in-Place-Upgrade zielt darauf ab, vorhandene Hardware-und Server Investitionen beizubehalten, wodurch die Gesamtkosten für die Bereitstellung von Skype for Business Server 2015 gesenkt werden.
  
> [!NOTE]
> Das direkte Upgrade ermöglicht Ihnen die Verwendung der gleichen Hardware beim Upgrade auf Skype for Business Server. Die Wiederverwendung derselben Hardware wird jedoch nicht in dieselbe Leistungskapazität übersetzt. Sie sollten nicht erwarten, dass die Leistungs Lasten für lync Server 2013 und Skype for Business Server 2015 identisch sind. 
  
> [!NOTE]
> Ein direktes Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. 
  
Das direkte Upgrade umfasst das offline schalten des lync Server 2013 Pools und das Upgrade auf einen Skype for Business Server 2015 Pool. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Erstellen eines in-Place-Aktualisierungsplans

Erstellen Sie einen Plan, der Folgendes umfasst:
  
1. Ein Verständnis der aktuellen Topologie.
    
    > [!NOTE]
    > Stellen Sie sicher, dass Sie das LRS-Verwaltungstool für lync Server 2013 deinstallieren, bevor Sie ein direktes Upgrade ausführen. Das LRS-Verwaltungs Tool für lync Server 2013 kann nicht mit Skype for Business Server 2015 koexistieren. Nachdem Sie das in-Place-Upgrade ausgeführt haben, installieren Sie das neue LRS-Verwaltungstool. Weitere Informationen finden Sie unter [Microsoft lync Room System administrative Webportal für Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) .
  
2. Der primäre Pool für das Upgrade.
    
3. Ob Sie die Archivierungs-und Überwachungsdatenbanken aktualisieren oder neue erstellen.
    
4. Die in-Place-Upgrade-Methode, die Sie verwenden: Offline oder Benutzer verlegen. Im Rahmen von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnisse migrieren, die dem primären Pool zugeordnet sind. 
    
5. Ein Kommunikationsplan für betroffene Benutzer.
    
6. Ein Sicherungsplan für den Fall, dass die Upgrades fehlschlagen.
    
Alle Benutzer, die sich im primären Pool befinden, während dieses aktualisiert wird, können die Dienste erst verwenden, wenn das Upgrade abgeschlossen ist. Wenn Sie über einen funktionierenden sekundären Pool verfügen, können Sie die Auswirkungen auf die Benutzer vermeiden, indem Sie Sie vor dem Upgrade in den sekundären Pool verschieben. Stellen Sie nach dem Upgrade die Benutzer wieder zurück in den primären Pool.
  
### <a name="in-place-upgrade-methods"></a>Methoden für das direktes Upgrade

Für ein direktes Upgrade stehen zwei Szenarien zur Verfügung: 
  
- Die Methode "Benutzer versetzen", die keine Ausfallzeit für Benutzer erfordert. 
    
- Die Offline-Methode, bei der Ausfallzeiten erforderlich sind.
    
Es wird empfohlen, ein Offline-Methoden Upgrade während eines Wartungsfensters einzuplanen, und die Benutzer werden über die Ausfallzeit informiert.
  
> [!NOTE]
> Wenn Sie einen gepaarten Pool auf lync Server 2013 aktualisieren und beide Pools auf Skype for Business Server 2015 aktualisieren möchten. Stellen Sie sicher, dass Sie den zweiten Pool sofort nach dem Upgrade des ersten Pools aktualisieren. Wenn ein Pool lync Server 2013 und der zweite Pool Skype for Business Server 2015 läuft, werden Notfallwiederherstellungsoptionen minimiert. Wenn beispielsweise ein Pool 2013 ausgeführt wird und der zweite 2015 und ein Notfall vorliegt, könnten Datenverluste auftreten, da das Pool Failover im Notfallmodus nicht unterstützt wird, wenn gekoppelte Pools nicht dieselbe Version sind. 
  
#### <a name="in-place-upgrade-offline-method"></a>Offline-Methode für direktes Upgrade

Verwenden Sie diese Methode, wenn Sie Benutzer nicht zwischen Benutzerpools bewegen möchten. Während des Upgrades können Benutzer lync-oder Skype for Business-Dienste nicht verwenden. 
  
Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
![Offline lync 2013 für Skype-Benutzer](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Wenn Sie gepaarte Pools haben, lassen Sie die Kopplung vor dem Upgrade nicht zu. 
  
Nachdem Sie mit dem Upgrade eines Server Pools begonnen haben, müssen Sie das Upgrade des gesamten Pools durchführen. Skype for Business Server unterstützt nicht, dass nur ein Teil des Pools aktualisiert wird. 
  
#### <a name="move-users-method-no-user-downtime"></a>Methode "Benutzer verlegen" (keine Ausfallzeit des Benutzers)
<a name="bkmk_MoveUsersMethod"> </a>

Um diese Methode verwenden zu können, müssen Sie Benutzer vor dem Upgrade in einen anderen Pool migrieren. Während des Upgrades können Benutzer lync-Dienste verwenden. Nachdem Sie in den aktualisierten Pool verschoben wurden, können Sie Skype for Business verwenden. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess.
  
> [!IMPORTANT]
> Im Rahmen von "Benutzer verschieben" müssen Sie auch die globalen Konferenzverzeichnisse migrieren, die dem primären Pool zugeordnet sind. PSTN-Einwahlkonferenzen werden weiterhin Konferenz-Nr in den Pool, der aktualisiert wird, und nicht auf den gekoppelten Pool aufgelöst. Sie müssen also Konferenzverzeichnisse umstellen, wenn Sie weiterhin festhalten möchten, dass im Pool geplante PSTN-Konferenzen während des Upgrades zugänglich sind. 
  
![Swim-Diagramm, das zeigt, dass Benutzer in einen anderen Pool verschoben werden, bevor der Pool aktualisiert wird und nach dem Upgrade wieder in den Pool verschoben wird.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Benutzer zur Hardwareaktualisierung migrieren
<a name="bkmk_MoveUsersMethod"> </a>

 Wenn Ihre Hardware nicht die [Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)erfüllt, richten Sie eine neue Skype for Business Server 2015 Umgebung ein, und legen Sie die Benutzer dorthin. Das folgende Diagramm zeigt eine Übersicht über diesen Prozess für ein Upgrade von lync Server 2010. 
  
![Diagramm zur Swim Lane, in dem Benutzer im lync Server primären Front-End-Pool in Skype for Business Server 2015 verschoben werden und der lync Server Pool außer Betrieb genommen wird.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Direkter Upgradevorgang

 Führen Sie die folgenden Schritte aus, um ein Upgrade von lync Server 2013 auf Skype for Business Server 2015 durchführen:
  
1. Sichern Sie alle Datenbanken vor dem Upgrade.
    
2. Stellen Sie sicher, dass alle Dienste, die aktualisiert werden sollen, den Status "ausgeführt" aufweisen.
    
3. Aktualisieren und veröffentlichen Sie die topologiedatei mithilfe des Topologie-Generators.
    
4. Beenden Sie alle Dienste auf allen Front-End-Servern.
    
5. Installieren Sie die für Skype for Business Server erforderlichen neuen Voraussetzungen.
    
6. Starten Sie auf jedem Front-End-Server das in-Place-Upgrade.
    
7. Wenn das Upgrade abgeschlossen ist, starten Sie alle Dienste neu.
    
   - Starten Sie für den Front-End-Pool Dienste mit dem Befehl Start-CsPool neu.
    
   - Verwenden Sie für nicht-Front-End-Server die Start-CSWindowsService.
    
> [!NOTE]
>  Wenn Sie Ihre vorhandenen Archivierungs-und Überwachungsdatenbanken nicht aktualisieren möchten, entfernen Sie die Abhängigkeit vor dem Upgrade der Topologie. Wenn Sie neue Archivierungs-und Überwachungsdatenbanken erstellen möchten, können Sie während des Upgrades einen neuen SQL-Speicher erstellen und ihn dem Pool zuordnen. Die Schritte zur Vorgehensweise finden Sie im Thema[Upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > in-Place-Upgrade unterstützt keine hohe Verfügbarkeit oder Notfallwiederherstellung für Skype for Business Server. Um die Benutzer Dienste nicht zu unterbrechen, verwenden Sie die [Methode "Benutzer verschieben" (keine Ausfallzeit des Benutzers)](upgrade.md#bkmk_MoveUsersMethod) , um ein Upgrade durchführen zu können. > während des Upgradevorgangs wird das XDS-Replikat im lokalen freigegebenen Ordner auf dem Laufwerk mit dem meisten freien Speicherplatz abgelegt. Wenn dieser Datenträger später entfernt wird, können Sie Probleme wie Dienste ausführen, die nicht gestartet werden.
  
### <a name="upgrade-order"></a>Upgrade-Reihenfolge

Aktualisieren Sie die Topologie von innen nach außen. Aktualisieren Sie zuerst alle Ihre Pools, dann die Edgeserver und schließlich den Pool zentraler Verwaltungsspeicher (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Überlegungen zur Kerberos-Authentifizierung

Wenn Sie die Kerberos-Authentifizierung für Webdienste verwenden, müssen Sie Kerberos-Konten neu zuweisen und das Kennwort zurücksetzen, nachdem das in-Place-Upgrade abgeschlossen ist. Weitere Informationen hierzu finden Sie unter Einrichten der [Kerberos-Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Unterstützung für die Koexistenz mit lync Server 2013 und lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Sie können Skype for Business Server 2015 in derselben Topologie wie lync Server 2013 oder lync Server 2010 ausführen, jedoch nicht alle drei in derselben Topologie.
  
Wenn Sie eine Koexistenz zwischen lync Server 2010 und lync Server 2013 haben, empfiehlt es sich, die gesamte Topologie auf lync Server 2013 zu aktualisieren und dann mithilfe des in-Place-Upgrades auf Skype for Business Server 2015 zu aktualisieren. Weitere Informationen finden Sie unter [Migration from lync Server 2010 to lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Wenn Ihre Topologie in erster Linie lync Server 2010 ist, setzen Sie die lync Server 2013 Komponenten auf lync Server 2010 zurück, bevor Sie die Topologie auf Skype for Business Server 2015 aktualisieren. In diesem Fall verlieren Sie den Vorteil des in-Place-Upgrades und verfügen über eine Koexistenz-Topologie zwischen lync Server 2010 und Skype for Business Server 2015.
  
Das folgende Diagramm zeigt die Koexistenz-Unterstützung von Skype for Business Server 2015 mit lync Server 2013 und lync Server 2010.
  
![Ein Diagramm mit der Unterstützung von nebeneinander für Skype for Business Server 2015 entweder mit lync Server 2013 oder lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Upgradeprozess mit vorhandener Survivable Branch Appliance und Server
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 unterstützt kein direktes Upgrade eines Survivable Branch Appliance (SBA) oder eines Survivable Branch Server (SBS).
  
Allerdings wird die Koexistenz von Skype for Business Server-Rechenzentren mit lync Server 2010 oder lync Server 2013 SBA/SBS unterstützt. 
  
Wenn Sie ein direktes Upgrade eines lync Server 2013-Front-End-Pools (Fe) mit einer zugeordneten Zweigstelle planen, können Sie die vorhandenen Benutzer im lync Server 2013 SBA/SBS belassen. Während des Upgrades werden die Benutzer von SBA/SBS im Ausfall Sicherheitsmodus wechseln und nach Abschluss des Upgrades zur normalen Funktionalität zurückkehren. Weitere Informationen zur Benutzererfahrung während des Ausfall Sicherheitsmodus finden Sie unter [Branch-Site Resilienz Features in lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Bei der Migration einer lync Server 2010 Topologie zu Skype for Business Server 2015 muss SBA/SBS der Topologie erneut hinzugefügt werden, ähnlich wie bei der Migration zu lync Server 2013. Die erforderlichen Schritte finden Sie unter [Connecting Survivable Branch Appliance to lync Server 2013 Front-End-Pool](https://technet.microsoft.com/library/jj688026.aspx).
  
Richten Sie für Koexistenz-Topologien von lync Server 2010 und lync Server 2013 zunächst die Empfehlungen im Abschnitt "Unterstützung der Koexistenz mit lync Server 2013 und lync Server 2010" aus.
  
## <a name="see-also"></a>Siehe auch
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Upgrade auf Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Umgebungsanforderungen für Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Server Anforderungen für Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
