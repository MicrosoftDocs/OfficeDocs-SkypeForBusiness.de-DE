---
title: 'Lync Server 2013: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung'
TOCTitle: Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398071(v=OCS.15)
ms:contentKeyID: 49292981
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-29_

Verwenden Sie das Cmdlet **Disable-CsAdDomain**, um die Domänenvorbereitung rückgängig zu machen.

## So machen Sie mithilfe von Cmdlets die Domänenvorbereitung rückgängig

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Beispiel:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Falls der Parameter "Force" vorhanden ist, wird auch dann ein Rollback der Domänenvorbereitung ausgeführt, wenn in der Domäne einer oder mehrere Front-End-Server oder A/V-Konferenzserver aktiviert sind. Falls der Parameter "Force" nicht vorhanden ist, wird der Rollback der Domänenvorbereitung beendet, wenn in der Domäne Front-End-Server oder A/V-Konferenzserver aktiviert sind.
    

    > [!NOTE]
    > Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Falls sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in den Active Directory-Domänendiensten (AD&nbsp;DS).



## Siehe auch

#### Aufgaben

[Ausführen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-running-domain-preparation.md)  

#### Weitere Ressourcen

[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

