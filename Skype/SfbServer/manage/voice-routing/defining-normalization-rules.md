---
title: Definieren von Normalisierungsregeln in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Reguläre Ausdrücke von .NET Framework nicht Skype für Normalisierungsregeln Business Server mit gewählten Telefonnummern in das e. 164-Format übersetzt wird. Anders ausgedrückt, Normalisierungsregeln übernehmen die von einem Benutzer gewählte Rufnummer und konvertieren diese Nummer in das Format von Skype für Business Server intern verwendet. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.
ms.openlocfilehash: 8e32ac485763c626d7d4347bb194fb4c4f3dba44
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882474"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype für Business Server

Reguläre Ausdrücke von .NET Framework nicht Skype für Normalisierungsregeln Business Server mit gewählten Telefonnummern in das e. 164-Format übersetzt wird. Anders ausgedrückt, Normalisierungsregeln übernehmen die von einem Benutzer gewählte Rufnummer und konvertieren diese Nummer in das Format von Skype für Business Server intern verwendet. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Wähleinstellungen und Normalisierungsregeln](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Ausführliche Informationen zum Schreiben Sie reguläre Ausdrücke finden Sie unter [Reguläre Ausdrücke von .NET Framework](http://go.microsoft.com/fwlink/p/?linkId=140927).

Sie können eine der folgenden Methoden verwenden, definieren oder bearbeiten eine Normalisierungsregel:
- [Verwenden Sie das Tool **Normalisierungsregel erstellen** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) , geben Sie Werte für die Anfangs-Ziffern, Länge, Ziffern zu entfernen und Ziffern hinzugefügt, und klicken Sie dann Skype Business Server-Systemsteuerung entsprechende übereinstimmenden und die übersetzungsregel zu generieren Für dich.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-normalization-rule-manually) in die entsprechenden und die übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mit Erstellen einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie erstellen oder Ändern einer Normalisierungsregel in Skype Business Server-Systemsteuerung möchten. 

**Um einer Regel definieren, indem Sie mit Erstellen einer Normalisierungsregel**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen hierzu finden Sie unter [Delegieren von setupberechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype für die Business-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. (Optional) Führen Sie die Schritte in [Erstellen Sie einen Dial Plan](GET LINK AFTER MIGRATION) bis Schritt 11 oder [Ändern eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 10. 
4. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (beispielsweise **5DigitExtension**).
5. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).
6. Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:
    - **Anfangsziffern**: (Optional) Geben Sie die führenden Ziffern Rufnummern, die Sie das Muster abgleichen möchten. Geben Sie beispielsweise **425** ein, wenn das Muster für gewählte Nummern gelten soll, die mit 425 beginnen.
    - **Länge**: Geben Sie die Anzahl der Nachkommastellen in die entsprechende Muster und wählen, ob Übereinstimmung Nummern beliebiger Länge gewählten Übereinstimmung Rufnummern, die mindestens diese Länge sind oder das Muster dieser Länge genau entsprechen soll.
    - **So entfernen Sie Ziffern**: (Optional) Geben Sie die Anzahl von Anfangsziffern ein, die aus gewählten Nummern entfernt werden Sie das Muster abgleichen möchten.
    - **Hinzuzufügende Ziffern**: Ziffern zu wählende Zahlen hinzugefügt werden soll (Optional) Geben Sie das Muster abgleichen möchten.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Beispielsweise wenn Sie **Starten Ziffern** leer lassen, Typ **7** in das Feld **Länge** wählen Sie **genau**, und geben Sie **0** in **Ziffern zu entfernen**, die resultierende reguläre Ausdruck in dem **Muster abgleichen** :

    **^(\d{7})$**

7. Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:
    - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn das Vergleichsmuster beispielsweise **^(\d{7})$**, und klicken Sie dann $1 in der übersetzungsregel gewählte Nummern 7 Ziffer darstellt.
    - (Optional) Geben Sie einen Wert in das Feld **Hinzuzufügende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden (z. B. **+1425**).
    
    Wenn enthält **Muster an,** beispielsweise **^(\d{7})$** wie das Muster für gewählter Nummern und **übersetzungsregel** enthält **+ 1425$ 1** dem Muster für e. 164-Rufnummern, übersetzt die Regel 5550100 in + 14255550100.

8. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.
9. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Weitere Informationen hierzu finden Sie unter [VoIP-routing testen](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.
12. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 
    > [!Note]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl Commit für alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen hierzu finden Sie unter [Veröffentlichen ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie manuell erstellen oder Ändern einer Normalisierungsregel möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen hierzu finden Sie unter [Delegieren von setupberechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL zum Öffnen der Systemsteuerung. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype für die Business-Systemsteuerung verwenden können, finden Sie unter [Installieren und open-Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. (Optional) Führen Sie die Schritte in [Erstellen Sie einen Dial Plan](GET LINK AFTER MIGRATION) bis Schritt 11 oder [Ändern eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 10.  
4. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (weisen Sie der Normalisierungsregel beispielsweise den Namen **5DigitExtension** zu).
5. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).
6. Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.
    - Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.

    Beispiel: bei Eingabe **^(\d{7})$** in **dieses Muster abgleichen** und **+ 1425$ 1** in **übersetzungsregel**übersetzt die Regel 5550100 in + 14255550100.

8. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.
9. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Weitere Informationen hierzu finden Sie unter [VoIP-routing testen](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx). 

10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.
12. Klicken Sie auf der Seite **Wählplan** auf **Commi**t und klicken Sie dann auf **Commit alle**. 
