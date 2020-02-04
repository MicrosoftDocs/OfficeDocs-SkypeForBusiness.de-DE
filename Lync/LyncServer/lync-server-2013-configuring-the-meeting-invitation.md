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
ms.openlocfilehash: 14e0614ecdaa73a886429e89618cac568d620938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Konfigurieren der Besprechungseinladung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-16_

Sie können vom Online Besprechungs-Add-in für lync 2013 gesendete Besprechungseinladungen anpassen, indem Sie die folgenden optionalen Elemente in den Textkörper der Besprechungseinladung einbeziehen:

  - **Das Logo Ihrer Organisation** Fügen Sie das Logo Ihrer Organisation zu Besprechungseinladungen hinzu, indem Sie die Option Logo-URL verwenden. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte sich das Bild in einer öffentlich verfügbaren URL befinden. Die unterstützten Bildformate sind GIF und JPG. Obwohl lync Server 2013 die URL ohne Größenbeschränkungen für das Bild speichert, sollte die maximale Größe des Bilds in Höhe von 30 Pixeln um 188 Pixel breit sein, um optimale Ergebnisse zu erzielen.

  - **Ein benutzerdefinierter Hilfe-oder Support Link** Fügen Sie eine URL für die Hilfe-oder Support Teamwebsite Ihrer Organisation hinzu. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein. Die maximale URL-Länge beträgt 1 KB.

  - **Rechtlicher Ausschluss Text** Fügen Sie eine URL für juristischen Text oder eine Verzichtserklärung hinzu, die in allen Besprechungseinladungen angezeigt wird. Wenn Besprechungseinladungen an Personen außerhalb Ihrer Organisation gesendet werden, sollte die URL öffentlich verfügbar sein. Die maximale URL-Länge beträgt 1 KB.

  - **Benutzerdefinierter Fußzeilentext** Fügen Sie Text hinzu, der in der Einladung als benutzerdefinierte Fußzeile gerendert wird. Die maximale Länge von Text, der hinzugefügt werden kann, ist 2 KB.

Sie können diese Optionen entweder mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell konfigurieren.

<div>


**So passen Sie die Besprechungseinladung mithilfe der lync Server-Systemsteuerung an**

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen** , und klicken Sie dann auf **besprechungskonfiguration**.

4.  Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
    
      - Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldienstes ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool und klicken Sie auf **OK**.

5.  Führen Sie einen der folgenden Schritte aus:
    
      - Geben Sie im Feld **Logo-URL** die URL für das Logo-Bild Ihrer Organisation ein.
    
      - Geben Sie im Feld **Hilfe-URL** die URL der Hilfe-oder Support Website Ihrer Organisation ein.
    
      - Geben Sie im Feld **rechtlicher Text** die URL für den rechtlichen Text oder die Verzichtserklärung ein, die Sie in Besprechungseinladungen einbeziehen möchten.
    
      - Geben Sie im Feld **benutzerdefiniertes Fußzeilen** Textfeld Fußzeilentext bis zu 2 KB ein.

**So passen Sie die Besprechungseinladung mithilfe der lync Server-Verwaltungsshell an**

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet " **New-CsMeetingConfiguration** " oder " **CsMeetingConfiguration** " aus, um die Besprechungs Einladungs Optionen zu erstellen oder zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

