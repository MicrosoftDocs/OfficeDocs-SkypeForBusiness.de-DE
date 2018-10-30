---
title: Suchen nach Lync Server-Benutzern
TOCTitle: Suchen nach Lync Server-Benutzern
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429701(v=OCS.15)
ms:contentKeyID: 49293736
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suchen nach Lync Server-Benutzern

 

_**Letztes Änderungsdatum des Themas:** 2014-05-14_

Mithilfe der Ergebnisse einer Suchabfrage können Sie Benutzer für Lync Server 2013 konfigurieren. Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.

Ferner können Sie Benutzer über die Lync Server-Systemsteuerung oder das Snap-In Active Directory-Benutzer und -Computer suchen. Im folgenden Verfahren wird beschrieben, wie Sie die Lync Server-Systemsteuerung zu diesem Zweck verwenden.


> [!NOTE]
> In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise ungenau, wenn Sie anhand der E-Mail-Adresse nach einem Benutzer suchen. Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z.&nbsp;B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet <STRONG>Get-CSUser</STRONG> verwenden.



## So suchen Sie nach einem oder mehreren Benutzern

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
    1.  Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um eine Benutzereigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf **Gleich** oder **Ungleich**.
    
    4.  Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.

6.  Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.

## Siehe auch

#### Weitere Ressourcen

[Anzeigen von Informationen zu Benutzerkonten, die für Lync Server 2013 aktiviert sind](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[Aktivieren und Deaktivieren von Benutzern für Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

