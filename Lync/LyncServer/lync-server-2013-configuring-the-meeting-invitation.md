---
title: 'Lync Server 2013: Konfigurieren der Besprechungseinladung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5697605b4560fc91a153869204756f0ddda356fc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Konfigurieren der Besprechungseinladung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-16_

Sie können vom Online-Besprechungs-Add-in gesendete Besprechungseinladungen für lync 2013 anpassen, indem Sie die folgenden optionalen Elemente im Text der Besprechungseinladung einschließen:

  - **Logo Ihrer Organisation** Fügen Sie das Logo Ihrer Organisation zu Besprechungseinladungen hinzu, indem Sie die Option Logo-URL verwenden. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte sich das Bild in einer öffentlich verfügbaren URL befinden. Die unterstützten Bildformate sind GIF und JPG. Obwohl lync Server 2013 die URL ohne Größenbeschränkungen für das Bild speichert, sollte die maximale Größe des Bilds für optimale Ergebnisse 30 Pixel hoch und 188 Pixel breit sein.

  - **Ein benutzerdefinierter Hilfe-oder Support Link** Fügen Sie eine URL für die Hilfe-oder Support Teamwebsite Ihrer Organisation hinzu. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein. Die maximale URL-Länge beträgt 1 KB.

  - **Rechtlicher Haftungsausschluss-Text** Fügen Sie eine URL für juristischen Text oder einen Haftungsausschluss hinzu, der in allen Besprechungseinladungen angezeigt wird. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein. Die maximale URL-Länge beträgt 1 KB.

  - **Benutzerdefinierter Fußzeilentext** Hinzufügen von Text, der in der Einladung als benutzerdefinierte Fußzeile gerendert wird. Die maximale Länge des Texts, der hinzugefügt werden kann, ist 2 KB.

Sie können diese Optionen entweder mit lync Server-Systemsteuerung oder lync Server-Verwaltungsshell konfigurieren.

<div>


**So passen Sie die Besprechungseinladung mithilfe von lync Server-Systemsteuerung an**

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **Besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **besprechungskonfiguration** auf **neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Websitekonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Feld **Website Suche auswählen** den vollständigen oder Teil des Namens der Website ein, für die Sie die Einstellungen für den besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
      - Klicken Sie zum Erstellen einer Richtlinie auf Poolebene auf **Poolkonfiguration**. Geben Sie im Suchfeld **Dienst auswählen einen** Teil oder den vollständigen Namen des Pool Diensts ein, für den Sie die Einstellungen für den besprechungsbeitritt definieren möchten. Klicken Sie in der daraufhin angezeigten Liste mit den Diensten auf den gewünschten Pool, und klicken Sie dann auf **OK**.

5.  Führen Sie einen der folgenden Schritte aus:
    
      - Geben Sie im Feld **Logo-URL** die URL des Logo Bilds Ihrer Organisation ein.
    
      - Geben Sie im Feld **Hilfe-URL** die URL zur Hilfe-oder Support Website Ihrer Organisation ein.
    
      - Geben Sie im Feld **juristischer Text** die URL des rechtlichen Texts oder Haftungsausschlusses ein, den Sie in Besprechungseinladungen einschließen möchten.
    
      - Geben Sie im **Textfeld benutzerdefinierter** Fußzeilentext Fußzeile ein, bis zu 2 KB.

**So passen Sie die Besprechungseinladung mithilfe von lync Server-Verwaltungsshell an**

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsMeetingConfiguration** oder **CsMeetingConfiguration** aus, um die Optionen für die Besprechungseinladung zu erstellen oder zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

