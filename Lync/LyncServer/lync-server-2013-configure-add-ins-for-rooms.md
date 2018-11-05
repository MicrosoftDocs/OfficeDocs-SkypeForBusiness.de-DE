---
title: 'Lync Server 2013: Konfigurieren von Add-Ins für Chatrooms'
TOCTitle: Konfigurieren von Add-Ins für Chatrooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204878(v=OCS.15)
ms:contentKeyID: 49293968
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Add-Ins für Chatrooms in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

In Systemsteuerung für Lync Server 2013 können Sie URLs mithilfe des Abschnitts **Add-In** auf der Seite **Beständiger Chat** einzelnen Beständiger Chat-Räumen zuweisen. Diese URLs werden im Lync 2013-Client des Chatrooms im Erweiterbarkeitsbereich für Unterhaltungen angezeigt. Administratoren müssen Add-Ins zur Liste der registrierten Add-Ins hinzufügen, und Chatroom-Manager/-Ersteller müssen die Räume mit einem der registrierten Add-Ins verknüpfen, bevor Benutzer diese Aktualisierung in Ihrem Lync 2013-Client sehen können.

Add-Ins erweitern die Möglichkeiten in Räumen. So kann ein typisches Add-In etwa eine URL enthalten, die auf eine Anwendung von Silverlight zeigt. Die Anwendung fängt dann beispielsweise die Veröffentlichung eines Börsenticker in einem Chatroom ab und zeigt den Kursverlauf im Erweiterbarkeitsbereich an. Eine andere Möglichkeit wäre die Einbindung einer OneNote 2013-URL in den Chatroom mithilfe eines Add-Ins, um bestimmte freigegebene Kontexte wie "Top-Priorität" oder "Thema des Tages" einzubinden.

## So konfigurieren Sie Add-ins für Chatrooms

1.  Melden Sie sich mit einem Benutzerkonto, das über die CsPersistentChatAdministrator- oder über die CsAdministrator-Rolle verfügt, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Wählen Sie im Menü **Start** die Lync Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Lync Server-Systemsteuerung anwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).
    

    > [!IMPORTANT]
    > Sie können auch Windows PowerShell-Cmdlets verwenden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets</A>.



3.  Klicken Sie im linken Bereich der Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In** .
    
    Bei Mehrfachbereitstellungen von Serverpool für beständigen Chat wählen Sie den entsprechenden Pool aus der Dropdownliste aus.

4.  Klicken Sie auf der Seite **Add-In** auf **Neu** .

5.  Wählen Sie unter **Dienst auswählen** den entsprechenden Dienst für den Serverpool für beständigen Chat aus, in dem das Add-In erstellt werden soll. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.

6.  Gehen Sie unter **Neues Add-In** wie folgt vor:
    
      - Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.
    
      - Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.

7.  Klicken Sie auf **Commit** .

## Siehe auch

#### Aufgaben

[Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md)  

#### Konzepte

[Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

