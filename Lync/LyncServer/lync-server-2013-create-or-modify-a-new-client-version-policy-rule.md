---
title: 'Lync Server 2013: Erstellen oder Ändern einer neuen clientversionsrichtlinien Regel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 732113537b79ad2ac767f64b861f296be508899c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512722"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Erstellen oder Ändern einer neuen clientversionsrichtlinien Regel in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-21_

Regeln für Client Versionsrichtlinien definieren die Aktionen, die ausgeführt werden sollten, wenn Benutzer versuchen, sich mit bestimmten Clients und Clientversionen anzumelden. Sie können in lync Server 2013 Systemsteuerung einzelne Regeln für eine clientversionsrichtlinie erstellen oder ändern.

<div>


> [!IMPORTANT]  
> Regeln werden in der Reihenfolge ihrer Rangfolge aufgeführt. Wenn Sie beispielsweise über eine Regel verfügen, mit der Clients, auf denen Version 1,5 ausgeführt wird, eine Verbindung herstellen können, gefolgt von einer Regel, die verhindert, dass Clients eine ältere Version als 2,0 ausgeführt haben, hat die erste Regel Vorrang, und Clients, auf denen Version 1,5 ausgeführt wird, können eine Verbindung herstellen.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>So erstellen oder ändern Sie clientversionsrichtlinien Regeln mit lync Server-Systemsteuerung

1.  [Erstellen oder ändern Sie eine neue clientversionsrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) mit lync Server-Systemsteuerung.

2.  Führen Sie auf der Seite **Client Versionsrichtlinie bearbeiten** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Neu**, um eine neue Clientversionsrichtlinie zu erstellen.
    
      - Klicken Sie auf einen der definierten Clienttypen in der Liste, und klicken Sie dann auf **Details einblenden**.
    
    <div>
    

    > [!NOTE]  
    > Sie können den Clienttyp mithilfe von Platzhalterzeichen angeben.

    
    </div>

3.  Wählen Sie unter **Benutzer-Agent** einen Clienttyp aus.

4.  Führen Sie unter **Versionsnummer** die folgenden Aktionen aus:
    
      - Geben Sie in **Hauptversion** die Nummer ein, die der Hauptversion des Clients entspricht.
    
      - Geben Sie in **Nebenversion** die Nummer ein, die der Nebenversion des Clients entspricht.
    
      - Geben Sie in **Build** die Nummer ein, die der Haupt- und Nebenversion des Clients entspricht.
    
      - Geben Sie in **Update** die Nummer ein, die der aktualisierten Version des Clients entspricht.
    
    <div>
    

    > [!NOTE]  
    > Sie können die Clientversionsnummer mithilfe von Platzhalterzeichen angeben.

    
    </div>

5.  Klicken Sie unter **Vergleichsvorgang** auf eine der folgenden Optionen, um den Vergleichsvorgang für die in den vorherigen Schritten angegebene Clientversion festzulegen:
    
      - **Gleich**
    
      - **Ungleich**
    
      - **Neuer als**
    
      - **Neuer als oder gleich**
    
      - **Älter als**
    
      - **Älter als oder gleich**

6.  Klicken Sie unter **Aktion** auf eine der folgenden Optionen, um die Aktion anzugeben, die bei Übereinstimmung mit dem angegebenen Kriterium ausgeführt werden soll:
    
      - Klicken Sie auf **Zulassen**, um die Anmeldung des Clients zu erlauben.
    
      - Klicken Sie auf **Zulassen und aktualisieren**, um dem Client die Anmeldung zu erlauben und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
        
        <div>
        

        > [!NOTE]  
        > Durch Auswahl dieser Aktion wird eine Benachrichtigung angezeigt, wenn sich Benutzer das nächste Mal bei lync 2013 anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

        
        </div>
    
      - Klicken Sie auf **Mit URL zulassen**, um die Anmeldung des Clients zu erlauben und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.
    
      - Um die Anmeldung des Clients zu verhindern, klicken Sie auf **Blockieren**.
    
      - Klicken Sie auf **Blockieren und aktualisieren**, um dem Client die Anmeldung zu verweigern und Updates über Windows Server Update Service oder Microsoft Update abzurufen. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt wurde.
    
      - Klicken Sie auf **Mit URL blockieren**, um die Anmeldung des Clients zu verweigern und den Benutzer in einer Meldung darauf hinzuweisen, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL später in diesem Verfahren an.

7.  (Optional) Wenn Sie im vorherigen Schritt auf **Mit URL zulassen** oder **Mit URL blockieren** geklickt haben, geben Sie unter **URL** die URL für den Clientdownload ein.

8.  Klicken Sie auf **OK** und dann auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

