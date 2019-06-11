---
title: 'Lync Server 2013: Ausführen der Domänenvorbereitung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Ausführen der Domänenvorbereitung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-04-16_

Sie können die Setup-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um Domänen vorzubereiten. Das Cmdlet, das eine Domäne vorbereitet, ist **enable-CsAdDomain**.

Die Domänenvorbereitung ist der letzte Schritt beim Vorbereiten der Active Directory-Domänendienste für lync Server 2013.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>So verwenden Sie das Setup zum Vorbereiten von Domänen

1.  Melden Sie sich bei einem beliebigen Server in der Domäne als Mitglied der Gruppe der Domänenadministratoren an.

2.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.

3.  Klicken Sie auf **Active Directory vorbereiten** und warten Sie das Bestimmen des Bereitstellungsstatus ab.

4.  Klicken Sie unter **Schritt 5: Aktuelle Domäne vorbereiten** auf **Ausführen**.

5.  Klicken Sie auf der Seite **Domäne vorbereiten** auf **weiter**.

6.  Suchen Sie auf der Seite **Befehle ausführen** nach **Aufgabenstatus: Abgeschlossen** und klicken Sie dann auf **Protokoll anzeigen**.

7.  Erweitern Sie in der Spalte " **Aktion** " die **Domäne prep**, suchen Sie nach einem ** \<\> ** Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Domänenvorbereitung erfolgreich abgeschlossen wurde, schließen Sie das Protokoll, und klicken Sie dann auf **Fertig stellen**.

8.  Warten Sie, bis die Active Directory-Replikation abgeschlossen ist, oder erzwingen Sie die Replikation auf alle Domänencontroller, die im Snap-in Active Directory-Standorte und-Dienste für den Gesamtstruktur-Stammdomänencontroller aufgeführt sind.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>So verwenden Sie Cmdlets zum Vorbereiten der Domäne

1.  Melden Sie sich bei einem beliebigen Server in der Domäne als Mitglied der Gruppe der Domänenadministratoren an.

2.  Installieren Sie die lync Server Core-Komponenten wie folgt:
    
    1.  Führen Sie im lync Server 2013-Installationsordner oder-Medium Setup. exe aus, um den lync Server-Bereitstellungs-Assistenten zu starten.
    
    2.  Wenn Sie aufgefordert werden, die Microsoft Visual C++-Installation zu installieren, klicken Sie auf **Ja**.
    
    3.  Im Dialogfeld "lync Server 2013-Setup" werden Sie aufgefordert, einen Speicherort zum Installieren der lync Server-Dateien anzuzeigen. Wählen Sie den Standardspeicherort aus, oder **Navigieren** Sie zu einem Speicherort Ihrer Wahl, und klicken Sie dann auf **Installieren**.
    
    4.  Aktivieren Sie auf der Seite Lizenzvertrag **die Kontrollkästchen Ich akzeptiere die Bedingungen des Lizenzvertrags**, und klicken Sie dann auf **OK**. Das Installationsprogramm installiert die lync Server 2013-Core-Komponenten.

3.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

4.  Führen Sie folgenden Befehl aus:
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    Beispiel:
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.

5.  Überprüfen Sie, ob die Domänenvorbereitung erfolgreich war. Führen Sie folgenden Befehl aus:
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    Beispiel:
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Mit dem Parameter GlobalSettingsDomainController können Sie angeben, wo die globalen Einstellungen gespeichert werden. Wenn Ihre Einstellungen im System Container gespeichert sind (typisch für Upgrade-Bereitstellungen, bei denen die globalen Einstellungen nicht in den Konfigurationscontainer migriert wurden), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Active Directory-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind und auf einen beliebigen Domänencontroller in&nbsp;AD DS verweisen.

    
    </div>
    
    Wenn Sie den Parameter **Domain** nicht angeben, ist der Standardwert die lokale Domäne.
    
    Dieses Cmdlet gibt den Wert des **LC\_-\_DOMAINSETTINGS\_-Status bereit** zurück, wenn die Domänenvorbereitung erfolgreich war.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwenden von Cmdlets zum Rückgängigmachen der Domänenvorbereitung für Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

