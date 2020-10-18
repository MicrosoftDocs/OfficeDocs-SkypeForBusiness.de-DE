---
title: 'Lync Server 2013: Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen'
description: 'Lync Server 2013: Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577961"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Erstellen oder Ändern einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Führen Sie die folgenden Schritte aus, wenn Sie eine Zugriffsnummer für Einwahlkonferenzen erstellen oder ändern möchten.

<div>


> [!IMPORTANT]  
> Bevor Sie eine neue Zugriffsnummer für die Einwahl erstellen, müssen Sie in den Wähleinstellungen, die der neuen Zugriffsnummer für die Einwahl zugeordnet sind, eine Region für Einwahlkonferenzen festlegen. In mehreren Wählplänen kann dieselbe Region verwendet werden.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>So erstellen oder ändern Sie eine Zugriffsnummer für die Einwahl

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Führen Sie auf der Seite **Zugriffsnummer für Einwahl** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **neu** , um eine **neue Zugriffsnummer für Einwahl**zu öffnen.
    
      - Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.
        
        <div>
        

        > [!NOTE]  
        > Wenn Sie das Suchfeld verwenden, um nach dem Inhalt einer Spalte in der Liste der Zugriffsnummern für Einwahlen zu suchen, ergeben sich möglicherweise nicht die erwarteten Ergebnisse. Sortieren Sie stattdessen die Liste nach der gewünschten Spalte, um die Zugriffsnummer für die Einwahl zu identifizieren, die Sie anzeigen oder ändern möchten.

        
        </div>

5.  Geben Sie unter **Anzeige Nummer**die Telefonnummer ein, die von Telefonbenutzern mit öffentlichem Telefonnetz (PSTN) gewählt wird, um an einer Konferenz teilzunehmen.
    
    <div>
    

    > [!NOTE]  
    > Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.

    
    </div>

6.  Geben Sie unter **Anzeigename**eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der der Zugriffsnummer für die Einwahl in lync-Suchergebnissen zugeordnet ist.
    
    <div>
    

    > [!NOTE]  
    > Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer anruft.

    
    </div>

7.  Geben Sie im Feld **Anschluss-URI**die E. 164-Nummer der Zugriffsnummer für die Einwahl im Tel-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispielsweise Tel: + 14255550200.
    
    <div>
    

    > [!NOTE]  
    > Derselbe Leitungs-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen verwendet werden.

    
    </div>

8.  Führen Sie unter **SIP-URI**die folgenden Schritte aus:
    
      - Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Orten angezeigt, einschließlich, aber nicht ausschließlich, Anrufbenachrichtigungen und vorherige Versionen von Communicator-Clients.
        
        <div>
        

        > [!NOTE]  
        > Derselbe SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nicht geändert werden, nachdem die Zugriffsnummer erstellt wurde. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.

        
        </div>
    
      - Klicken Sie im Dropdown-Listenfeld auf die Domäne der Konferenzzentrale, die diese Zugriffsnummer für die Einwahl unterstützt.

9.  Klicken Sie unter **Pool**auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Zugriffsnummer für die Einwahl unterstützt.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet " <STRONG>CsApplicationEndpoint</STRONG> " verwenden oder die Zugriffsnummer löschen und neu erstellen.

    
    </div>

10. Klicken Sie in der **primären Sprache**auf die Sprache, in der Eingabeaufforderungen für diese Zugriffsnummer für die Einwahl wiedergegeben werden.
    
    <div>
    

    > [!NOTE]  
    > Die primäre Sprache ist die Sprache, die die Konferenzzentrale verwendet, um den Anruf entgegenzunehmen. Unterstützte Sprachen werden neben jeder Access-Telefonnummer auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.

    
    </div>

11. Optional Klicken Sie in **sekundären Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer für diese Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können eine sekundäre Sprache auswählen, bevor Sie die Konferenz-ID eingeben, wenn Sie sich in eine Konferenz einwählen.

    
    </div>

12. Klicken Sie zum Hinzufügen einer Region für die Zugriffsnummer für die Einwahl unter **zugeordnete Regionen**auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Zugriffsnummer für die Einwahl zugeordnet sind, und klicken Sie dann auf **OK**.

13. Wenn Sie eine Region aus der Zugriffsnummer für die Einwahl löschen möchten, klicken Sie unter **zugeordnete Regionen**auf die Region, die Sie löschen möchten, und klicken Sie dann auf **Entfernen**.

14. Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

