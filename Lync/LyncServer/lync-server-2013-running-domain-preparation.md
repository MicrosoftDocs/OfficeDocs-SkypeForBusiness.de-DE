---
title: 'Lync Server 2013: Ausführung der Domänenvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960a3664bb7b629a9d66b375d072f826ed9e2738
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Ausführung der Domänenvorbereitung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-04-16_

Sie können Setup-oder lync Server-Verwaltungsshell-Cmdlets zum Vorbereiten von Domänen verwenden. Das Cmdlet, das eine Domäne vorbereitet, ist **Enable-CsAdDomain**.

Die Domänenvorbereitung ist der letzte Schritt bei der Vorbereitung Active Directory-Domänendienste auf lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>So verwenden Sie Setup zum Vorbereiten von Domänen

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten**, und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

5.  Klicken Sie auf der Seite **Domäne vorbereiten** auf **Weiter**.

6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen**, und klicken Sie dann auf **Protokoll anzeigen**.

7.  Erweitern Sie in der Spalte **Aktion** den Knoten **Domänenvorbereitung**, suchen Sie nach einem ** \<\> ** Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

8.  Warten Sie auf den Abschluss der Active Directory-Replikation, oder erzwingen Sie die Replikation für alle Domänencontroller, die im Snap-In "Active Directory-Standorte und -Dienste" für den Domänencontroller des Gesamtstrukturstamms aufgelistet sind.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>So verwenden Sie Cmdlets zum Vorbereiten der Domäne

1.  Melden Sie sich als Mitglied der Gruppe der Domänenadministratoren bei einem beliebigen Server an.

2.  Installieren Sie lync Server Kernkomponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013 Installationsordner oder auf dem Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Klicken Sie auf **Ja**, wenn Sie zur Installation von Microsoft Visual C++ Redistributable aufgefordert werden.
    
    3.  Im Dialogfeld Setup für lync Server 2013 werden Sie aufgefordert, einen Speicherort für die lync Server Dateien zu installieren. Wählen Sie den Standardspeicherort, oder klicken Sie auf **Durchsuchen**, um einen anderen Speicherort anzugeben, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite "Lizenzvertrag" die Option **Ich stimme den Bedingungen des Lizenzvertrags zu**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013 Kernkomponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Ausführen
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Beispiel:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.

5.  Überprüfen Sie, ob die Domänenvorbereitung erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Beispiel:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Über den Parameter "GlobalSettingsDomainController" können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, in denen die globalen Einstellungen nicht zum Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänen&nbsp;Controller in AD DS.

    
    </div>
    
    Wenn Sie den Parameter **Domain** nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Dieses Cmdlet gibt einen Wert von **LC\_DOMAINSETTINGS\_Status\_Ready** zurück, wenn die Domänenvorbereitung erfolgreich war.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

