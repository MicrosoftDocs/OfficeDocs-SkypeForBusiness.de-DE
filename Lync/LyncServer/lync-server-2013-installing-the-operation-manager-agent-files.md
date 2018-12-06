---
title: Installieren der Operations Manager-Agent-Dateien
TOCTitle: Installieren der Operations Manager-Agent-Dateien
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205345(v=OCS.15)
ms:contentKeyID: 49295681
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren der Operations Manager-Agent-Dateien

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Führen Sie die folgenden Schritte aus, um die Operations Manager-Agentdateien auf dem Computer zu installieren.

1.  Doppelklicken Sie auf den System Center-Setupmedien auf **SetupOM.exe**.

2.  Klicken Sie im System Center Operations Manager-Setupprogramm auf **Operations Manager-Agent installieren**.

3.  Klicken Sie im System Center-Setup-Assistenten auf der Willkommensseitedes Assistenten auf **Weiter**.

4.  Wählen Sie auf der Seite **Zielordner** den Ordner aus, in dem die Operations Manager-Agentdateien installiert werden sollen, und klicken Sie dann auf **Weiter**.

5.  Wählen Sie auf der Seite **Verwaltungsgruppenkonfiguration** die Option **Verwaltungsgruppeninformationen angeben** aus, und klicken Sie dann auf **Weiter**.

6.  Geben Sie auf der Seite **Verwaltungsgruppenkonfiguration** den Namen Ihrer Operations Manager-Verwaltungsgruppe im Feld **Verwaltungsgruppenname** ein. Geben Sie anschließend im Feld **Verwaltungsserver** den Hostnamen Ihres Operations Manager-Servers ein (z. B. atl-scom-001). Falls Sie die von Operations Manager verwendete Portnummer geändert haben, geben Sie die neue Portnummer im Feld Verwaltungsserverport ein. Lassen Sie andernfalls für den Port den Standardwert 5723 eingestellt, und klicken Sie auf **Weiter**.

7.  Wählen Sie auf der Seite **Agentaktionskonto** die Option **Lokales System** aus, und klicken Sie dann auf **Weiter**.

8.  Wählen Sie auf der Seite **Microsoft Update** die Option **Ich möchte Microsoft Update nicht verwenden** aus, und klicken Sie dann auf **Weiter**.

9.  Klicken Sie auf der Seite **Bereit zum Installieren** auf **Installieren**.

10. Klicken Sie auf der Seite **Fertigstellen des System Center Operations Manager-Setup-Assistenten** auf **Fertig stellen**.

11. Klicken Sie auf **Beenden**.

Falls Sie System Center 2007 R2 verwenden, können Sie überprüfen, ob der Agent erstellt wurde. Klicken Sie dazu auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf**System Center Operations Manager 2007 R2**, und klicken Sie dann auf **Operations Manager-Shell**. Geben Sie in der Operations Manager-Shell den folgenden Windows PowerShell-Befehl ein, und drücken Sie dann die EINGABETASTE:

    Get-Agent 

Eine Liste aller Operations Manager-Agents wird angezeigt.

Falls Sie System Center 2012 verwenden, führen Sie den folgenden Befehl in der Operations Manager 2012-Shell aus:

    Get-SCOMAgent

