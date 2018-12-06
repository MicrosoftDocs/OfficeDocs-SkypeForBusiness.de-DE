---
title: 'Lync Server 2013: Ausführen der Domänenvorbereitung'
TOCTitle: Ausführen der Domänenvorbereitung
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398761(v=OCS.15)
ms:contentKeyID: 49294806
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ausführen der Domänenvorbereitung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-04-16_

Für die Vorbereitung von Domänen können Sie Setup oder Lync Server-Verwaltungsshell-Cmdlets nutzen. Das Cmdlet, das eine Domäne vorbereitet, ist **Enable-CsAdDomain**.

Die Domänenvorbereitung ist der abschließende Schritt bei der Vorbereitung von Active Directory-Domänendienste für Lync Server 2013.

## So verwenden Sie Setup zum Vorbereiten von Domänen

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Lync Server-Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten** , und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen** .

5.  Klicken Sie auf der Seite **Domäne vorbereiten** auf **Weiter** .

6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** , und klicken Sie dann auf **Protokoll anzeigen** .

7.  Erweitern Sie in der Spalte **Aktion** die Option **Domänenvorbereitung** , und achten Sie hinter jeder Aufgabe auf das Ausführungsergebnis **\<Erfolg\>** , um sicherzustellen, dass die Domänenvorbereitung erfolgreich abgeschlossen wurde. Schließen Sie das Protokoll, und klicken Sie auf **Fertig stellen** .

8.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In "Active Directory-Standorte und -Dienste" für den Domänencontroller des Gesamtstrukturstamms aufgelistet sind.

## So verwenden Sie Cmdlets zum Vorbereiten der Domäne

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Installieren Sie die Lync Server-Hauptkomponenten wie folgt:
    
    1.  Führen Sie im Lync Server 2013-Installationsordner oder auf dem Installationsmedium "Setup.exe" aus, um den Lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja** , wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Sie werden im Dialogfeld für das Lync Server 2013-Setup aufgefordert, einen Speicherort für die Installation der Lync Server-Dateien anzugeben. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen** , um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren** .
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** , und klicken Sie dann auf **OK** . Das Installationsprogramm installiert die Hauptkomponenten von Lync Server 2013.

3.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Beispiel:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

5.  Überprüfen Sie, ob die Domänenvorbereitung erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Beispiel:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    

    > [!NOTE]
    > Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in AD&nbsp;DS.

    
    Wenn Sie den Parameter **Domain** nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Bei erfolgreicher Domänenvorbereitung gibt dieses Cmdlet den Wert **LC\_DOMAINSETTINGS\_STATE\_READY** zurück.

## Siehe auch

#### Aufgaben

[Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  

#### Weitere Ressourcen

[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

