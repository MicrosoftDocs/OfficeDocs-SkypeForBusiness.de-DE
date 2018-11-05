---
title: Erstellen oder Ändern von Netzwerkstandorten
TOCTitle: Erstellen oder Ändern von Netzwerkstandorten
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520975(v=OCS.15)
ms:contentKeyID: 49293643
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern von Netzwerkstandorten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die Systemsteuerung für Microsoft Lync Server 2013 verwenden, um Standorte zu konfigurieren und Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. Über die Lync Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen Netzwerkstandort zu erstellen oder zu ändern. Ausführliche Informationen zum Löschen eines vorhandenen Netzwerkstandorts finden Sie unter [Löschen eines vorhandenen Netzwerkstandorts](lync-server-2013-deleting-an-existing-network-site.md).

## So erstellen Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf **Neu**.

5.  Geben Sie unter **Neuer Standort** im Feld **Name** einen Namen für den Standort ein.
    

    > [!NOTE]
    > Standortnamen müssen innerhalb der Lync Server 2013-Bereitstellung eindeutig sein.



6.  Wählen Sie in der Dropdownliste **Region** eine Netzwerkregion aus, die diesem Standort zugeordnet werden soll.

7.  (Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe für diesen Standort festlegen möchten, wählen Sie das Bandbreitenrichtlinienprofil mit den passenden Einstellungen in der Dropdownliste **Bandbreitenrichtlinie** aus.
    

    > [!NOTE]
    > Auf der Seite <STRONG>Richtlinienprofil</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Bandbreitenrichtlinienprofile anzeigen oder ein neues Bandbreitenrichtlinienprofil erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Erstellen oder Ändern von Bandbreitenrichtlinienprofilen</A>.



8.  (Optional) Wenn Sie Ortungseinstellungen für diesen Standort bereitstellen möchten, wählen Sie in der Dropdownliste **Ortungsrichtlinie** eine Ortungsrichtlinie aus.
    

    > [!NOTE]
    > Die Ortungsrichtlinie weist dem Standort bestimmte E9-1-1- und Clientstandorteinstellungen zu. Auf der Seite <STRONG>Ortungsrichtlinie</STRONG> in der Gruppe <STRONG>Netzwerkkonfiguration</STRONG> können Sie die Details der verfügbaren Ortungsrichtlinien anzeigen oder eine neue Ortungsrichtlinie erstellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-viewing-location-policy-information.md">Anzeigen von Informationen zu Ortungsrichtlinien</A>.



9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Standort ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit**.
    

    > [!NOTE]
    > Beim Erstellen eines neuen Netzwerkstandorts verwenden Sie nicht die Tabelle <STRONG>Zugeordnete Subnetze</STRONG>. Sie ordnen einem Standort ein Subnetz zu, wenn Sie das Subnetz erstellen oder ändern. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-network-subnets.md">Erstellen oder Ändern von Netzwerksubnetzen</A>.



## So ändern Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Standort bearbeiten** können Sie die Beschreibung, die Region, das Bandbreitenrichtlinienprofil und die Ortungsrichtlinie für den Standort ändern. Ausführliche Informationen hierzu finden Sie unter "So erstellen Sie einen Netzwerkstandort" weiter oben in diesem Thema.

7.  Klicken Sie auf **Commit**.

Sie können die Tabelle **Zugeordnete Subnetze** auf dieser Seite nicht ändern. Die Liste der zugeordneten Subnetze wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Subnetze sich die Änderung der Standorteinstellungen auswirkt.

## So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]
    > Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>.



## Siehe auch

#### Aufgaben

[Löschen eines vorhandenen Netzwerkstandorts](lync-server-2013-deleting-an-existing-network-site.md)  

#### Weitere Ressourcen

[New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)  
[Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)  
[Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)  
[Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

