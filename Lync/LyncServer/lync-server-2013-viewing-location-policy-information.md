---
title: Anzeigen von Informationen zu Ortungsrichtlinien
TOCTitle: Anzeigen von Informationen zu Ortungsrichtlinien
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520954(v=OCS.15)
ms:contentKeyID: 49293268
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Ortungsrichtlinien

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In Lync Server 2013 können Sie mit der Ortungsrichtlinie Einstellungen im Zusammenhang mit der Funktion "9-1-1 (erweitert) (E9-1-1)" und den Standorteinstellungen für Benutzer oder Kontakte zuweisen. Die Ortungsrichtlinie ermittelt, ob E9-1-1 für einen Benutzer aktiviert ist, und legt ggf. das Verhalten eines Notrufs fest. Sie können mit der Ortungsrichtlinie beispielsweise definieren, welche Nummer als Notrufnummer betrachtet wird (z. B. 911), ob die Abteilung für Unternehmenssicherheit automatisch benachrichtigt und wie der Anruf weitergeleitet werden soll.

Sie können Ortungsrichtlinien in der Systemsteuerung für Lync Server 2013 in der Gruppe **Netzwerkkonfiguration** konfigurieren. In der Lync Server-Systemsteuerung können Ortungsrichtlinien angezeigt, erstellt, geändert und gelöscht werden. Verwenden Sie das folgende Verfahren, um Informationen zu Ortungsrichtlinien anzuzeigen. Nähere Informationen zum Erstellen oder Ändern von Ortungsrichtlinien finden Sie unter [Erstellen oder Ändern einer Ortungsrichtlinie](lync-server-2013-creating-or-modifying-a-location-policy.md).

## So zeigen Sie Informationen zu einer Ortungsrichtlinie an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.
    

    > [!NOTE]
    > Sie können jeweils nur Informationen zu einer Ortungsrichtlinie anzeigen.



Standardmäßig ist eine einzige Richtlinie (Global) vorhanden, die nicht gelöscht oder umbenannt werden kann. Sie können die globale Richtlinie jedoch ändern. Sofern keine Standortrichtlinien oder Richtlinien auf Benutzerbasis erstellt werden, wird diese Richtlinie auf sämtliche Benutzer und Kontakte angewendet. Richtlinien auf Benutzerbasis müssen auf bestimmte Benutzer angewendet werden.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Ortungsrichtlinie](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Erstellen von Ortungsrichtlinien in Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  

#### Weitere Ressourcen

[New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsLocationPolicy)

