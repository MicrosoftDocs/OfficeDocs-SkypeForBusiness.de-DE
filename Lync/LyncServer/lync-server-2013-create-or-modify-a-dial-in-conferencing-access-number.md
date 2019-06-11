---
title: 'Lync Server 2013: Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8372c8117f2e33594ae59b3eff15c6d7eee96ba6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Führen Sie die folgenden Schritte aus, wenn Sie eine Access-Nummer für Einwahlkonferenzen erstellen oder ändern möchten.

<div>


> [!IMPORTANT]  
> Bevor Sie eine neue Einwahl Zugriffsnummer erstellen, müssen Sie in dem Wählplan, der der neuen Einwahl Zugriffsnummer zugeordnet ist, einen Bereich für Einwahlkonferenzen einrichten. Mehrere Wählpläne können denselben Bereich verwenden.



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>So erstellen oder ändern Sie eine Einwahl Zugriffsnummer

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Einwahlnummer**.

4.  Führen Sie auf der Seite **Einwahlnummer** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Neu**, um **Neue Einwahlnummer** zu öffnen.
    
      - Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
        
        <div>
        

        > [!NOTE]  
        > Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten.

        
        </div>

5.  Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen.
    
    <div>
    

    > [!NOTE]  
    > Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.

    
    </div>

6.  Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der der Einwahl Zugriffsnummer in den lync-Suchergebnissen zugeordnet ist.
    
    <div>
    

    > [!NOTE]  
    > Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt.

    
    </div>

7.  Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    <div>
    

    > [!NOTE]  
    > Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden.

    
    </div>

8.  Führen Sie unter **SIP-URI** die folgenden Aktionen aus:
    
      - Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht ausschließlich, von Benachrichtigungsnachrichten und früheren Versionen von Communicator-Clients.
        
        <div>
        

        > [!NOTE]  
        > Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.

        
        </div>
    
      - Klicken Sie im Dropdown-Listenfeld auf die Domäne der Conferencing Attendant-Anwendung, die diese Einwahl Zugriffsnummer unterstützt.

9.  Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.
    
    <div>
    

    > [!NOTE]  
    > Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> verwenden oder die Zugriffsnummer löschen und neu erstellen.

    
    </div>

10. Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden.
    
    <div>
    

    > [!NOTE]  
    > Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.

    
    </div>

11. (Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.
    
    <div>
    

    > [!NOTE]  
    > Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.

    
    </div>

12. Wenn Sie einen Bereich für die Einwahl Zugriffsnummer hinzufügen möchten, klicken Sie unter **zugeordnete Regionen**auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahl Zugriffsnummer zugeordnet sind, und klicken Sie dann auf **OK**.

13. Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.

14. Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

