---
title: 'Lync Server 2013: Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen'
TOCTitle: Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398126(v=OCS.15)
ms:contentKeyID: 49293066
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Einwahlnummer für Einwahlkonferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Führen Sie die folgenden Schritte aus, um eine Einwahlnummer für Einwahlkonferenzen zu erstellen oder zu ändern.


> [!IMPORTANT]
> Vor dem Erstellen einer neuen Zugriffsnummer für die Einwahl müssen Sie eine Region für Einwahlkonferenzen in den Wähleinstellungen festlegen, die der neuen Zugriffsnummer für die Einwahl zugeordnet sind. Eine Region kann von mehreren Sätzen mit Wähleinstellungen verwendet werden.



## So erstellen oder ändern Sie eine Einwahlnummer

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Einwahlnummer**.

4.  Führen Sie auf der Seite **Einwahlnummer** einen der folgenden Schritte aus:
    
      - Klicken Sie auf **Neu**, um **Neue Einwahlnummer** zu öffnen.
    
      - Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.
        

        > [!NOTE]
        > Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten.



5.  Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen.
    

    > [!NOTE]
    > Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.



6.  Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dieser Name wird der Zugriffsnummer für die Einwahl in den Lync-Suchergebnissen zugeordnet.
    

    > [!NOTE]
    > Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt.



7.  Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    

    > [!NOTE]
    > Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden.



8.  Führen Sie unter **SIP-URI** die folgenden Aktionen aus:
    
      - Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Stellen angezeigt, z. B. in Anrufbenachrichtigungen sowie in früheren Versionen von Communicator-Clients.
        

        > [!NOTE]
        > Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.

    
      - Klicken Sie im Dropdown-Listenfeld auf die Domäne der Konferenzzentrale, die diese Einwahlnummer unterstützt.

9.  Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.
    

    > [!NOTE]
    > Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet <STRONG>Move-CsApplicationEndpoint</STRONG> verwenden oder die Zugriffsnummer löschen und neu erstellen.



10. Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden.
    

    > [!NOTE]
    > Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.



11. (Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen** , wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK** .
    

    > [!NOTE]
    > Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.



12. Klicken Sie unter **Zugeordnete Regionen** auf **Hinzufügen** , klicken Sie auf eine oder mehrere Regionen, die den Wähleinstellungen für diese Zugriffsnummer für die Einwahl zugeordnet sind, und klicken Sie anschließend auf **OK** , um eine Region für die Zugriffsnummer hinzuzufügen.

13. Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.

14. Klicken Sie auf **Commit ausführen**.

