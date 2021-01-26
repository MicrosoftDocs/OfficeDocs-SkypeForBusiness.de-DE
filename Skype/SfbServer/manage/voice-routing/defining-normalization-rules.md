---
title: Definieren von Normalisierungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Normalisierungsregeln für Skype for Business Server verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Normalisierungsregeln verwenden also die von einem Benutzer gewählte Telefonnummer und konvertieren diese Nummer in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823375"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype for Business Server

Normalisierungsregeln für Skype for Business Server verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E.164-Format zu übersetzen. Normalisierungsregeln verwenden also die von einem Benutzer gewählte Telefonnummer und konvertieren diese Nummer in das intern von Skype for Business Server verwendete Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Weitere Informationen zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln.](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)

Weitere Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework Regular Expressions](https://go.microsoft.com/fwlink/p/?linkId=140927).

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:
- Verwenden Sie das Tool zum Erstellen einer [  Normalisierungsregel,](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die Skype for Business Server-Systemsteuerung das entsprechende Vergleichsmuster und die Übersetzungsregel für Sie generieren.
- [Schreiben Sie reguläre Ausdrücke manuell,](#create-or-modify-a-normalization-rule-manually) um das Vergleichsmuster und die Übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe von "Normalisierungsregel erstellen"

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in der Skype for Business Server-Systemsteuerung erstellen oder ändern möchten. 

**So definieren Sie eine Regel mithilfe von "Normalisierungsregel erstellen"**

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) bis Schritt 11 oder [Ändern eines](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) Wählplans bis Schritt 10 aus. 
4. Geben **Sie in "Neue** Normalisierungsregel" oder **"Normalisierungsregel** bearbeiten" einen Namen ein, der das normalisierte Nummernmuster **im** Namen beschreibt (z. B. **5DigitExtension**).
5. (Optional) Geben **Sie** in "Beschreibung" eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").
6. Geben **Sie in "Normalisierungsregel** erstellen" Werte in die folgenden Felder ein:
    - **Anfangsziffern:**(Optional) Geben Sie die führenden Ziffern gewählter Nummern an, die mit dem Muster übereinstimmen. Geben Sie beispielsweise **425 ein,** wenn das Muster mit gewählten Nummern übereinstimmen soll, die mit 425 beginnen.
    - **Länge:** Geben Sie die Anzahl der Ziffern im Vergleichsmuster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, ob es mit gewählten Nummern mit mindestens dieser Länge oder mit gewählten Nummern beliebiger Länge übereinstimmen soll.
    - **Zu entfernende** Ziffern: (Optional) Geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.
    - **Hinzuzufügende** Ziffern: (Optional) Geben Sie Ziffern an, die gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.
    
    Die Werte, die Sie in diesen Feldern eingeben, werden in **"Muster für Übereinstimmung"** und **"Übersetzungsregel" angezeigt.** Wenn Sie z.  B. die Anfangsziffern leer lassen, geben Sie **7** **in** das Feld **"Länge"** die Option "Genau" **ein,** und geben Sie **"0"** in zu entfernenden Ziffern an. Der resultierende reguläre Ausdruck im Muster, der übereinstimmen soll, ist: 

    **^(\d {7} )$**

7. Geben **Sie in der** Übersetzungsregel ein Muster für das Format übersetzter E.164-Telefonnummern wie folgt an:
    - Ein Wert, der die Anzahl der Im Vergleichsmuster angegebenen Ziffern darstellt. Wenn das Vergleichsmuster beispielsweise **^(\d {7} )$** ist, stellt $1 in der Übersetzungsregel siebenstellige gewählte Nummern dar.
    - (Optional) Geben Sie einen Wert in das Feld **"Ziffern"** ein, um die Ziffern anzugeben, die der übersetzten Nummer voranstellen sollen (z. B. **+1425**).
    
    Wenn "Muster  für Übereinstimmung" beispielsweise **^(\d {7} )$** als  Muster für gewählte Nummern enthält und die Übersetzungsregel **+1425$1** als Muster für E.164-Telefonnummern enthält, normalisiert die Regel 5550100 in +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer internen Telefonnummer in Ihrer Organisation führt, wählen Sie interne **Durchwahl aus.**
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Weitere Informationen finden Sie unter ["Testen des Voiceroutings".](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Klicken Sie **auf "OK",** um die Normalisierungsregel zu speichern.
11. Klicken Sie **auf "OK",** um den Wählplan zu speichern.
12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**. 
    > [!Note]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl "Commit für alle" ausführen, um die Konfigurationsänderung zu veröffentlichen. Weitere Informationen finden Sie unter [Veröffentlichen ausstehender Änderungen an der Voiceroutingkonfiguration.](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx) 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Weitere Informationen finden Sie unter [Delegieren von Setupberechtigungen.](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Systemsteuerung zu öffnen. Weitere Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter "Installieren und Öffnen [von Verwaltungstools".](../../management-tools/install-and-open-administrative-tools.md)
3. (Optional) Führen Sie die Schritte unter [Erstellen eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 11 oder [Ändern eines](GET LINK AFTER MIGRATION) Wählplans bis Schritt 10 aus.  
4. Geben **Sie in** "Neue Normalisierungsregel" oder **"Normalisierungsregel** bearbeiten" einen Namen ein, der das normalisierte Nummernmuster **im** Namen beschreibt (nennen Sie beispielsweise die Normalisierungsregel **"5DigitExtension").**
5. (Optional) Geben **Sie** in "Beschreibung" eine Beschreibung der Normalisierungsregel ein (z. B. "Übersetzt 5-stellige Erweiterungen").
6. Klicken **Sie in "Normalisierungsregel erstellen"** auf **"Bearbeiten".**
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben **Sie in Diesem Muster** das Muster an, das Sie verwenden möchten, um der gewählten Telefonnummer zu entsprechen.
    - Geben **Sie in der** Übersetzungsregel ein Muster für das Format übersetzter E.164-Telefonnummern an.

    Wenn Sie beispielsweise **^(\d {7} )$** **in** Übereinstimmung mit diesem Muster und **+1425$1** **in** der Übersetzungsregel eingeben, normalisiert die Regel 5550100 in +14255550100.

8. (Optional) Wenn die Normalisierungsregel zu einer internen Telefonnummer in Ihrer Organisation führt, wählen Sie interne **Durchwahl aus.**
9. (Optional) Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **"Los".** Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht bestanden hat, und sie später neu konfigurieren. Weitere Informationen finden Sie unter ["Testen des Voiceroutings".](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx) 

10. Klicken Sie **auf "OK",** um die Normalisierungsregel zu speichern.
11. Klicken Sie **auf "OK",** um den Wählplan zu speichern.
12. Klicken Sie **auf der Seite "Wählplan"** **auf "Commi** t", und klicken Sie dann **auf Commit für alle**. 
