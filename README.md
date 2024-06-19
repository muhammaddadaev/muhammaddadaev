pip install python-pptx
from pptx import Presentation
from pptx.util import Inches
import subprocess

# Create a presentation object
prs = Presentation()

# Slide 1: Title Slide
slide_layout = prs.slide_layouts[0]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
subtitle = slide.placeholders[1]
title.text = "STAFFLINK EUROPE Sp. z o.o."
subtitle.text = "Profesjonalne usługi HR i outsourcingu"
slide.shapes.add_picture('path/to/team_professional.jpg', Inches(2), Inches(2.5), width=Inches(6))

# Slide 2: About Us
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "O nas"
content = slide.placeholders[1]
content.text = (
    "STAFFLINK EUROPE Sp. z o.o. to wiodąca agencja zatrudnienia i outsourcingu. "
    "Nasza misja to dostarczanie najwyższej jakości usług HR, które pomagają firmom osiągać sukcesy. "
    "Nasza wizja to być najlepszym partnerem w zarządzaniu personelem."
)
slide.shapes.add_picture('path/to/company_team.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Slide 3: Our Services
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "Nasze usługi"
content = slide.placeholders[1]
content.text = (
    "- Rekrutacja specjalistów\n"
    "- Zarządzanie zatrudnieniem\n"
    "- Outsourcing personelu"
)
slide.shapes.add_picture('path/to/services.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Slide 4: Why Us?
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "Dlaczego my?"
content = slide.placeholders[1]
content.text = (
    "Korzyści współpracy z nami:\n"
    "- Dostęp do wysokiej jakości kandydatów\n"
    "- Oszczędność czasu i zasobów\n"
    "- Wsparcie ekspertów"
)
slide.shapes.add_picture('path/to/happy_clients.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Slide 5: Cooperation Process
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "Proces współpracy"
content = slide.placeholders[1]
content.text = (
    "Krok po kroku:\n"
    "1. Analiza potrzeb klienta\n"
    "2. Selekcja kandydatów\n"
    "3. Zatrudnienie i onboarding\n"
    "4. Stałe wsparcie i rozwój pracowników"
)
slide.shapes.add_picture('path/to/process.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Slide 6: Our Successes
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "Nasze sukcesy"
content = slide.placeholders[1]
content.text = (
    "Przykłady udanych projektów:\n"
    "- Projekt A: Zatrudnienie 50 specjalistów IT\n"
    "- Projekt B: Outsourcing dla międzynarodowej korporacji\n"
    "Referencje od klientów dostępne na życzenie."
)
slide.shapes.add_picture('path/to/success.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Slide 7: Contact
slide_layout = prs.slide_layouts[1]
slide = prs.slides.add_slide(slide_layout)
title = slide.shapes.title
title.text = "Kontakt"
content = slide.placeholders[1]
content.text = (
    "STAFFLINK EUROPE Sp. z o.o.\n"
    "Żurawia 32/34, biuro 511, 00-515 Warszawa\n"
    "Tel: +48 501 545 141\n"
    "Tel: +48 22 243 3509\n"
    "E-mail: stafflinkeurope@gmail.com"
)
slide.shapes.add_picture('path/to/office.jpg', Inches(0.5), Inches(2.5), width=Inches(9))

# Save the presentation
pptx_path = "STAFFLINK_EUROPE_prezentacja.pptx"
prs.save(pptx_path)

# Convert to PDF using LibreOffice
pdf_path = "STAFFLINK_EUROPE_prezentacja.pdf"
subprocess.run(["libreoffice", "--headless", "--convert-to", "pdf", pptx_path])

print(f"PDF saved as {pdf_path}")
python create_presentation.py
