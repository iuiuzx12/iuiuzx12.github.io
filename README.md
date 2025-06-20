<!DOCTYPE html>
<html lang="th" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CS50x: The Genesis (ฉบับเจาะลึก)</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Sarabun:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Sarabun', sans-serif; font-weight: 400; }
        h1, h2, h3, h4, h5, h6 { font-weight: 600; }
        .content-card { background-color: white; border-radius: 0.75rem; box-shadow: 0 4px_6px_-1px_rgb(0_0_0_/_0.1),_0_2px_4px_-2px_rgb(0_0_0_/_0.1); padding: 2rem; margin-bottom: 2rem; }
        .code-block { background-color: #1E293B; color: #E2E8F0; padding: 1rem; border-radius: 0.5rem; font-family: 'Courier New', Courier, monospace; font-size: 0.9em; white-space: pre-wrap; word-break: break-word; }
        .code-block div { min-height: 1.2em; }
        .code-keyword, .keyword-glossary { color: #60A5FA; font-weight: bold; }
        .keyword-glossary { border-bottom: 1px dotted #60A5FA; cursor: pointer; }
        .code-function { color: #A78BFA; }
        .code-comment { color: #64748B; }
        .code-string { color: #A3E635; }
        .code-placeholder { color: #FBBF24; font-weight: bold; }
        #glossary-modal-backdrop { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.5); z-index: 99; display: none; }
        #glossary-modal { position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%); background-color: white; padding: 2rem; border-radius: 0.5rem; box-shadow: 0 10px 25px rgba(0,0,0,0.1); width: 90%; max-width: 500px; z-index: 100; display: none; }
    </style>
</head>
<body class="bg-slate-50 text-slate-800">

    <div class="container mx-auto max-w-4xl p-4 sm:p-6 lg:p-8">
        <header class="text-center mb-12">
            <h1 class="text-5xl font-extrabold text-sky-800 mb-2">CS50x: The Genesis</h1>
            <p class="text-xl text-slate-600">จากแนวคิดสู่ "Hello, World!" และการสนทนาโต้ตอบ</p>
        </header>

        <main>
            <section id="intro" class="scroll-mt-16">
                <div class="content-card">
                    <h2 class="text-3xl font-bold text-slate-900 mb-4">บทที่ 1: ศิลปะแห่งการแก้ปัญหา (The Art of Problem-Solving)</h2>
                    <p class="text-slate-600 mb-4 leading-relaxed">ก่อนที่เราจะเขียนโปรแกรมใดๆ ในโลก เราต้องเรียนรู้ทักษะที่สำคัญกว่านั้น นั่นคือศิลปะในการ **แก้ปัญหา** ครับ ลองจินตนาการว่าคุณมีหุ่นยนต์ที่ซื่อสัตย์แต่... โง่เขลาเบาปัญญามาก คุณไม่สามารถสั่งมันว่า "ไปซื้อกาแฟให้หน่อย" ได้ เพราะมันไม่เข้าใจคำว่า "ซื้อ" หรือ "กาแฟ" เลย</p>
                    <p class="text-slate-600 mb-4 leading-relaxed">คุณต้องแตกปัญหานี้ออกเป็นขั้นตอนที่เล็กและโง่ที่สุดเท่าที่จะทำได้ นี่แหละครับคือหัวใจของ <strong class="text-sky-600">Computational Thinking</strong></p>
                    
                    <div class="bg-slate-50 border border-slate-200 p-6 rounded-lg my-6">
                        <h3 class="text-xl font-semibold text-slate-800 mb-3">Input → Process → Output: หัวใจของทุกโปรแกรม</h3>
                        <p class="mb-4">ทุกสิ่งทุกอย่างที่คอมพิวเตอร์ทำ สามารถมองเป็นกระบวนการง่ายๆ 3 ขั้นตอนนี้ได้เสมอครับ ลองนึกถึง "ตู้กดน้ำอัดลม" ดูสิครับ:</p>
                        <div class="bg-white p-6 rounded-lg flex flex-col md:flex-row items-start justify-around text-center gap-4">
                            <div class="flex flex-col items-center">
                                <div class="text-4xl">⌨️</div>
                                <p class="font-semibold mt-2">1. Input (ข้อมูลนำเข้า)</p>
                                <p class="text-sm text-slate-600">คุณใส่เหรียญและกดปุ่ม 'C4' นี่คือข้อมูลที่คุณป้อนเข้าไป</p>
                            </div>
                            <div class="text-2xl text-slate-400 font-light my-4 md:my-0 md:mt-8">→</div>
                            <div class="flex flex-col items-center">
                                <div class="text-4xl">🧠</div>
                                <p class="font-semibold mt-2">2. Process (ประมวลผล)</p>
                                <p class="text-sm text-slate-600">กลไกข้างในตู้ทำงาน มันเช็กว่าเงินพอไหม, หาว่า 'C4' คืออะไร, แล้วสั่งให้เกลียวหมุน นี่คือ "สมอง" ของโปรแกรม หรือที่เราเรียกว่า <strong class="keyword-glossary" data-term="Algorithm" data-def="ชุดของขั้นตอนที่ชัดเจนและมีลำดับ สำหรับใช้แก้ปัญหาหรือทำงานให้สำเร็จ เหมือนสูตรทำอาหารที่ต้องทำตามเป๊ะๆ">Algorithm</strong></p>
                            </div>
                            <div class="text-2xl text-slate-400 font-light my-4 md:my-0 md:mt-8">→</div>
                            <div class="flex flex-col items-center">
                                <div class="text-4xl">🖥️</div>
                                <p class="font-semibold mt-2">3. Output (ผลลัพธ์)</p>
                                <p class="text-sm text-slate-600">กระป๋องน้ำอัดลมตกลงมาที่ช่องรับของ นี่คือผลลัพธ์ที่จับต้องได้</p>
                            </div>
                        </div>
                    </div>

                    <h3 class="text-xl font-semibold text-slate-800 mt-8 mb-3">เครื่องมือในกล่องของนักคิด (The Toolbox)</h3>
                    <p class="text-slate-600 mb-4 leading-relaxed">และถึงแม้ Algorithm ของเราจะซับซ้อนแค่ไหน เครื่องมือที่เราต้องใช้ในการสร้างมันขึ้นมาจริงๆ มีเพียง 3 อย่างนี้เท่านั้นครับ:</p>
                    <ul class="space-y-4">
                        <li><strong>ฟังก์ชัน (Functions):</strong> ลองนึกว่าคุณกำลังเขียน "ตำราอาหาร" แทนที่จะเขียนวิธี "หั่นหอมหัวใหญ่" ซ้ำๆ ในทุกๆ สูตรอาหาร คุณก็แค่เขียนวิธีหั่นไว้ในบทแรกบทเดียว แล้วตั้งชื่อให้มันว่า "วิธีหั่นหอม" ต่อไปในสูตรอื่นๆ คุณก็แค่เขียนว่า "ไปดูวิธีหั่นหอมจากบทแรก" พอ! ฟังก์ชันก็คือสิ่งเดียวกันครับ มันคือการตั้งชื่อให้ "ชุดของขั้นตอน" ที่เราทำบ่อยๆ เพื่อให้เราเรียกใช้ได้โดยไม่ต้องเขียนซ้ำ</li>
                        <li><strong>เงื่อนไข (Conditionals):</strong> ชีวิตเต็มไปด้วยทางแยก โปรแกรมก็เช่นกันครับ `if-else` คือเครื่องมือที่ช่วยให้โปรแกรมตัดสินใจได้ เช่น `<strong class="text-amber-600">ถ้า</strong> ตู้เย็นมีไข่ <strong class="text-amber-600">ก็ให้</strong>ทำไข่เจียว, <strong class="text-amber-600">แต่ถ้าไม่ ก็ให้</strong>ทำข้าวผัด` มันคือการสร้างทางเลือกให้โปรแกรมของเรา ไม่ใช่การเดินไปข้างหน้าอย่างเดียว</li>
                        <li><strong>ลูป (Loops):</strong> ลองจินตนาการว่าคุณต้องตีไข่ 50 ครั้ง คงไม่มีใครอยากเขียนคำสั่ง "ตีไข่" 50 บรรทัดใช่ไหมครับ? เราก็แค่สั่งว่า `<strong class="text-lime-600">ทำซ้ำ 50 ครั้ง:</strong> ตีไข่` นี่คือการใช้ `loop` ครับ มันคือเครื่องมือที่ทรงพลังที่สุดในการจัดการกับงานที่ต้องทำซ้ำๆ</li>
                    </ul>
                    <p class="mt-6 text-slate-700 font-medium">เมื่อเราเข้าใจศิลปะในการคิดและเครื่องมือทั้ง 3 อย่างนี้แล้ว... เราก็พร้อมที่จะเรียนรู้ "ภาษา" ที่จะใช้สื่อสารความคิดเหล่านี้กับคอมพิวเตอร์แล้วล่ะครับ และภาษานั้นก็คือ C</p>
                </div>
            </section>

            <section id="c-basics" class="scroll-mt-16">
                 <div class="content-card">
                    <h2 class="text-3xl font-bold text-slate-900 mb-4">บทที่ 2: การสนทนาครั้งแรก (Anatomy of C)</h2>
                    <h3 class="text-xl font-semibold mb-3">ทำไมต้องเป็นภาษา C ที่ดูน่ากลัว?</h3>
                    <p class="text-slate-600 mb-4 leading-relaxed">
                        ภาษาโปรแกรมสมัยใหม่ๆ ก็เหมือน "รถยนต์เกียร์ออโต้" ครับ ขับง่าย สะดวกสบาย มันจัดการเรื่องน่าปวดหัวให้เราหมด แต่... คุณไม่เคยได้สัมผัสการทำงานของเครื่องยนต์จริงๆ เลย คุณไม่รู้ว่าเกียร์เปลี่ยนตอนไหน หรือทำไมรอบเครื่องถึงขึ้น
                    </p>
                    <p class="text-slate-600 mb-4 leading-relaxed">
                        ส่วนภาษา C ก็เหมือน **"รถยนต์เกียร์กระปุก"** ครับ คุณต้องเหยียบคลัตช์เอง เข้าเกียร์เอง คุณต้องฟังเสียงเครื่องยนต์ คุณต้องรู้สึกถึงแรงสั่นสะเทือน มันอาจจะยากกว่าในตอนแรก แต่มันบังคับให้คุณต้องเข้าใจ "จิตวิญญาณ" ของยานยนต์อย่างแท้จริง และเมื่อคุณขับเป็น... คุณจะสามารถรีดประสิทธิภาพของรถออกมาได้สูงสุด การเรียน C ก็เพื่อให้เราได้ "เปิดฝากระโปรง" และเห็นการทำงานของคอมพิวเตอร์ในระดับที่ลึกที่สุดนั่นเองครับ
                    </p>
                    
                    <h3 class="text-xl font-semibold mt-8 mb-3">การสนทนาครั้งแรก: ผ่าตัดโปรแกรม Hello, world!</h3>
                    <p class="text-slate-600 mb-4">เอาล่ะครับ ถึงเวลาที่เราจะมาผ่าตัดโค้ดโปรแกรมแรกของเรากันแบบละเอียดยิบทุกอณู นี่คือบทสนทนาแรกระหว่างเรากับคอมพิวเตอร์ (ลองคลิกที่คำศัพท์สีฟ้าเหมือนเดิมนะครับ!)</p>
                     <div class="code-block">
                        <div><span class="code-comment">// บรรทัดนี้เหมือนการบอกว่า "เฮ้ คอมไพเลอร์! ก่อนจะเริ่มทำงาน</span></div>
                        <div><span class="code-comment">// ช่วยไปหยิบ 'กล่องเครื่องมือมาตรฐาน' สำหรับการ Input/Output มาให้ทีนะ"</span></div>
                        <div>
                            <span class="keyword-glossary" data-term="#include" data-def="คำสั่ง 'พรีโปรเซสเซอร์' ใช้บอกคอมไพเลอร์ว่า 'ช่วยไปเอาโค้ดจากไฟล์อื่นมารวมกับไฟล์นี้ที' เหมือนการไปหยิบกล่องเครื่องมือมาเตรียมไว้ใช้งาน">#include</span>
                            <span class="code-string"> &lt;<span class="keyword-glossary" data-term="stdio.h" data-def="ชื่อของ 'กล่องเครื่องมือ' มาตรฐาน (Standard Input/Output Header) ที่มีฟังก์ชันพื้นฐานอย่าง printf() อยู่ข้างใน">stdio.h</span>&gt;</span>
                        </div>
                        <div>&nbsp;</div>
                        <div><span class="code-comment">// นี่คือ "จุดสตาร์ท" ของโปรแกรมเราครับ ทุกอย่างจะเริ่มทำงานจากตรงนี้</span></div>
                        <div>
                            <span class="keyword-glossary" data-term="int" data-def="ย่อมาจาก Integer คือชนิดของข้อมูลที่เป็น 'เลขจำนวนเต็ม' การระบุ int หน้า main หมายความว่าเมื่อฟังก์ชันนี้ทำงานเสร็จ จะต้อง 'คืนค่า' กลับไปเป็นเลขจำนวนเต็ม">int</span>
                            <span class="keyword-glossary code-function" data-term="main" data-def="คือชื่อฟังก์ชันที่พิเศษที่สุด ถือเป็น 'ประตูทางเข้าหลัก' ของทุกโปรแกรมในภาษา C คอมพิวเตอร์จะมองหาฟังก์ชัน main() เป็นอันดับแรกเสมอ">main</span>
                            <span class="keyword-glossary" data-term="()" data-def="วงเล็บที่ตามหลังชื่อฟังก์ชัน ใช้สำหรับใส่ 'อาร์กิวเมนต์' หรือข้อมูลที่เราต้องการส่งเข้าไปให้ฟังก์ชันทำงาน ถ้าไม่มีอะไรจะส่ง ก็จะใส่ void ไว้ข้างใน">(</span><span class="keyword-glossary" data-term="void" data-def="แปลว่า 'ว่างเปล่า' ในที่นี้หมายความว่าฟังก์ชัน main ไม่ต้องการรับข้อมูลใดๆ จากภายนอกเพื่อเริ่มทำงาน">void</span><span class="keyword-glossary" data-term="()" data-def="วงเล็บที่ตามหลังชื่อฟังก์ชัน ใช้สำหรับใส่ 'อาร์กิวเมนต์' หรือข้อมูลที่เราต้องการส่งเข้าไปให้ฟังก์ชันทำงาน ถ้าไม่มีอะไรจะส่ง ก็จะใส่ void ไว้ข้างใน">)</span>
                        </div>
                        <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด ทุกอย่างที่อยู่ระหว่างปีกกาเปิด { และปีกกาปิด } ถือว่าเป็นส่วนหนึ่งของบล็อกนั้นๆ"> {</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// นี่คือคำสั่งที่เราเรียกใช้เครื่องมือจากกล่อง stdio.h</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// เพื่อ "พิมพ์" ข้อความในวงเล็บออกไปที่หน้าจอ</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary code-function" data-term="printf" data-def="มาจาก Print-Formatted เป็นฟังก์ชันที่อยู่ใน stdio.h ใช้สำหรับแสดงผลข้อความหรือค่าของตัวแปรออกไปยังหน้าจอ">printf</span>
                            (<span class="code-string">"Hello, world!\n"</span>)<span class="keyword-glossary" data-term=";" data-def="เซมิโคลอน คือเครื่องหมาย 'จบประโยค' ในภาษา C มันทำหน้าที่เหมือนจุด full-stop ในภาษาอังกฤษ เพื่อบอกคอมไพเลอร์ว่าคำสั่งนี้จบลงแล้ว">;</span>
                        </div>
                        <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด ทุกอย่างที่อยู่ระหว่างปีกกาเปิด { และปีกกาปิด } ถือว่าเป็นส่วนหนึ่งของบล็อกนั้นๆ">}</span></div>
                    </div>
                </div>
            </section>
            
            <section id="c-interactive" class="scroll-mt-16">
                <div class="content-card">
                    <h2 class="text-3xl font-bold text-slate-900 mb-4">บทที่ 3: การสนทนาโต้ตอบ (Interactive Conversations)</h2>
                    <p class="text-slate-600 mb-4 leading-relaxed">
                        ยินดีด้วยครับ! ตอนนี้คุณสามารถส่ง "ข้อความ" ไปยังคอมพิวเตอร์ได้แล้ว แต่การสื่อสารที่ดีคือการสื่อสารสองทางใช่ไหมครับ? ในบทนี้ เราจะทำให้โปรแกรมของเรา "ฉลาด" ขึ้น โดยการรับข้อมูลจากผู้ใช้กลับมาบ้าง และนี่คือการเติมเต็มโมเดล `Input -> Process -> Output` ของเราให้สมบูรณ์
                    </p>
                    <h3 class="text-xl font-semibold mt-8 mb-3">กล่องมหัศจรรย์: ตัวแปร (Variables)</h3>
                     <p class="text-slate-600 mb-4 leading-relaxed">
                        ลองจินตนาการว่าคุณต้องการให้โปรแกรมถามชื่อของคุณ แล้วทักทายกลับมาด้วยชื่อนั้น... โปรแกรมจะ "จำ" ชื่อที่คุณพิมพ์เข้าไปได้อย่างไร? คำตอบคือ <strong class="keyword-glossary" data-term="Variable" data-def="ตัวแปร คือชื่อที่เราตั้งขึ้นมาเพื่ออ้างอิงถึงพื้นที่ในหน่วยความจำของคอมพิวเตอร์ ใช้สำหรับเก็บข้อมูลที่โปรแกรมต้องใช้งาน เปรียบเสมือนกล่องที่มีป้ายชื่อกำกับอยู่">ตัวแปร (Variable)</strong> ครับ
                    </p>
                    <p class="text-slate-600 mb-4 leading-relaxed">
                        ตัวแปร ก็เหมือน "กล่องเปล่าพร้อมป้ายชื่อ" ครับ เราต้องทำ 2 อย่าง:
                    </p>
                     <ul class="space-y-2 list-disc list-inside mb-4">
                        <li><strong>ตั้งชื่อให้กล่อง (Declare a variable):</strong> เราต้องบอกคอมพิวเตอร์ก่อนว่า "ฉันจะสร้างกล่องนะ กล่องนี้ชื่อว่า `name`"</li>
                        <li><strong>บอกชนิดของที่จะใส่ (Specify data type):</strong> ที่สำคัญ เราต้องบอกด้วยว่ากล่องนี้จะเอาไว้ใส่ของ "ประเภท" ไหน เช่น ใส่ข้อความ (<strong class="keyword-glossary" data-term="string" data-def="ชนิดข้อมูลสำหรับเก็บ 'ข้อความ' หรือ 'ชุดของตัวอักษร' ในไลบรารีของ CS50 ทำให้การจัดการข้อความเป็นเรื่องง่าย">string</strong>) หรือใส่ตัวเลข (<strong class="keyword-glossary" data-term="int" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' (Integer) เช่น -1, 0, 5, 100">int</strong>)</li>
                    </ul>

                    <h3 class="text-xl font-semibold mt-8 mb-3">สนทนากับผู้ใช้: โค้ดทักทายอัจฉริยะ</h3>
                    <p class="text-slate-600 mb-4">
                        มาดูโปรแกรมที่สมบูรณ์ขึ้นกันครับ โปรแกรมนี้จะถามชื่อของคุณ แล้วนำชื่อนั้นมาแสดงผลบนหน้าจอ จะเห็นว่าเราได้หยิบ "กล่องเครื่องมือ" มาเพิ่มอีกหนึ่งชิ้นคือ `<cs50.h>` ซึ่งเป็นไลบรารีพิเศษของคอร์ส CS50 ที่ทำให้การรับ Input ง่ายขึ้นมากครับ
                    </p>
                    <div class="code-block">
                        <div><span class="code-comment">// หยิบกล่องเครื่องมือมาตรฐาน และกล่องเครื่องมือพิเศษของ CS50</span></div>
                        <div>
                            <span class="keyword-glossary" data-term="#include" data-def="คำสั่ง 'พรีโปรเซสเซอร์' ใช้บอกคอมไพเลอร์ว่า 'ช่วยไปเอาโค้ดจากไฟล์อื่นมารวมกับไฟล์นี้ที' เหมือนการไปหยิบกล่องเครื่องมือมาเตรียมไว้ใช้งาน">#include</span>
                            <span class="code-string"> &lt;<span class="keyword-glossary" data-term="cs50.h" data-def="ไลบรารี (กล่องเครื่องมือ) พิเศษของ CS50 ที่มีฟังก์ชันอำนวยความสะดวก เช่น get_string(), get_int() ทำให้การรับข้อมูลจากผู้ใช้ทำได้ง่ายขึ้นมาก">cs50.h</span>&gt;</span>
                        </div>
                         <div>
                            <span class="keyword-glossary" data-term="#include" data-def="คำสั่ง 'พรีโปรเซสเซอร์' ใช้บอกคอมไพเลอร์ว่า 'ช่วยไปเอาโค้ดจากไฟล์อื่นมารวมกับไฟล์นี้ที' เหมือนการไปหยิบกล่องเครื่องมือมาเตรียมไว้ใช้งาน">#include</span>
                            <span class="code-string"> &lt;<span class="keyword-glossary" data-term="stdio.h" data-def="ชื่อของ 'กล่องเครื่องมือ' มาตรฐาน (Standard Input/Output Header) ที่มีฟังก์ชันพื้นฐานอย่าง printf() อยู่ข้างใน">stdio.h</span>&gt;</span>
                        </div>
                        <div>&nbsp;</div>
                        <div>
                            <span class="keyword-glossary" data-term="int" data-def="ย่อมาจาก Integer คือชนิดของข้อมูลที่เป็น 'เลขจำนวนเต็ม' การระบุ int หน้า main หมายความว่าเมื่อฟังก์ชันนี้ทำงานเสร็จ จะต้อง 'คืนค่า' กลับไปเป็นเลขจำนวนเต็ม">int</span>
                            <span class="keyword-glossary code-function" data-term="main" data-def="คือชื่อฟังก์ชันที่พิเศษที่สุด ถือเป็น 'ประตูทางเข้าหลัก' ของทุกโปรแกรมในภาษา C คอมพิวเตอร์จะมองหาฟังก์ชัน main() เป็นอันดับแรกเสมอ">main</span>
                            (<span class="keyword-glossary" data-term="void" data-def="แปลว่า 'ว่างเปล่า' ในที่นี้หมายความว่าฟังก์ชัน main ไม่ต้องการรับข้อมูลใดๆ จากภายนอกเพื่อเริ่มทำงาน">void</span>)
                        </div>
                        <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด ทุกอย่างที่อยู่ระหว่างปีกกาเปิด { และปีกกาปิด } ถือว่าเป็นส่วนหนึ่งของบล็อกนั้นๆ"> {</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// 1. สร้าง 'กล่อง' ชนิด string ชื่อว่า name</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">//&nbsp;&nbsp;&nbsp;&nbsp;และใช้ฟังก์ชัน get_string เพื่อรับข้อความจากผู้ใช้มาใส่ในกล่อง</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary" data-term="string" data-def="ชนิดข้อมูลสำหรับเก็บ 'ข้อความ' หรือ 'ชุดของตัวอักษร' ในไลบรารีของ CS50 ทำให้การจัดการข้อความเป็นเรื่องง่าย">string</span>
                            name = 
                            <span class="keyword-glossary code-function" data-term="get_string" data-def="ฟังก์ชันจากไลบรารี cs50.h ใช้สำหรับรับข้อมูลประเภทข้อความ (string) จากผู้ใช้">get_string</span>
                            (<span class="code-string">"What's your name? "</span>);
                        </div>
                        <div>&nbsp;</div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// 2. พิมพ์คำว่า "hello, " แล้วตามด้วยสิ่งที่อยู่ในกล่อง name</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary code-function" data-term="printf" data-def="มาจาก Print-Formatted เป็นฟังก์ชันที่อยู่ใน stdio.h ใช้สำหรับแสดงผลข้อความหรือค่าของตัวแปรออกไปยังหน้าจอ">printf</span>
                            (<span class="code-string">"hello, <span class="keyword-glossary code-placeholder" data-term="%s" data-def="เรียกว่า 'Format Specifier' เป็นตัวจองที่ในข้อความ เพื่อบอก printf ว่า 'ตรงนี้นะ เดี๋ยวจะเอาค่า string มาเสียบแทนที่'">%s</span>\n"</span>, name);
                        </div>
                         <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด ทุกอย่างที่อยู่ระหว่างปีกกาเปิด { และปีกกาปิด } ถือว่าเป็นส่วนหนึ่งของบล็อกนั้นๆ">}</span></div>
                    </div>
                     <p class="mt-6 text-center text-lg text-slate-700 font-medium">ยอดเยี่ยมมากครับ! ตอนนี้เว็บไซต์ของเราได้นำพาผู้เรียนจากการเป็นเพียงผู้ส่งสารฝ่ายเดียว มาสู่การเป็นผู้สร้างบทสนทนาที่สมบูรณ์แล้ว</p>
                </div>
            </section>
            
            <section id="c-calculator" class="scroll-mt-16">
                <div class="content-card">
                    <h2 class="text-3xl font-bold text-slate-900 mb-4">บทที่ 4: คอมพิวเตอร์คิดเลข (Calculations & Data Types)</h2>
                    <p class="text-slate-600 mb-4 leading-relaxed">
                        นอกจากการจัดการกับ "ข้อความ" แล้ว พลังที่แท้จริงของคอมพิวเตอร์คือการ "คำนวณ" ครับ ในบทนี้ เราจะเปลี่ยนคอมพิวเตอร์ให้กลายเป็นเครื่องคิดเลขส่วนตัวของเรา แต่ก่อนอื่น เราต้องรู้จัก "ชนิด" ของตัวเลขที่คอมพิวเตอร์เข้าใจกันก่อน
                    </p>
                    <h3 class="text-xl font-semibold mt-8 mb-3">ตัวเลขก็มีหลายประเภท (Numeric Data Types)</h3>
                     <p class="text-slate-600 mb-4 leading-relaxed">
                        ในโลกคณิตศาสตร์มีทั้งเลขจำนวนเต็มและเลขทศนิยม ในภาษา C ก็เช่นกันครับ เราต้องเลือกใช้ "กล่อง" หรือตัวแปรให้ถูกประเภทกับตัวเลขที่เราจะเก็บ
                    </p>
                     <ul class="space-y-3 list-disc list-inside mb-4">
                        <li><strong class="keyword-glossary" data-term="int" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' (Integer) เช่น -1, 0, 5, 100 ไม่มีจุดทศนิยม">int</strong>: สำหรับเก็บเลข **จำนวนเต็ม** เช่น `5`, `200`, หรือ `-10` เหมือนการนับจำนวนคนหรือจำนวนของที่ไม่สามารถแบ่งเป็นเศษส่วนได้</li>
                        <li><strong class="keyword-glossary" data-term="float" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขทศนิยม' (Floating-point number) เช่น 3.14, -0.5, 99.99">float</strong>: สำหรับเก็บเลข **ทศนิยม** เช่น `3.14` หรือ `1.75` เหมาะกับข้อมูลที่ต้องการความละเอียดอย่างส่วนสูงหรือเกรดเฉลี่ย</li>
                        <li><strong class="keyword-glossary" data-term="long" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' ที่มีขนาดใหญ่มาก (Long Integer) ใหญ่กว่าที่ int ทั่วไปจะเก็บได้">long</strong>: สำหรับเก็บเลขจำนวนเต็มที่ **ใหญ่มากๆ** เกินกว่าที่ `int` ธรรมดาจะรับไหว</li>
                    </ul>

                    <h3 class="text-xl font-semibold mt-8 mb-3">เครื่องมือของนักคำนวณ: ตัวดำเนินการ (Operators)</h3>
                    <p class="text-slate-600 mb-4">
                        ภาษา C มีเครื่องหมายสำหรับการคำนวณเหมือนกับที่เราเรียนคณิตศาสตร์มาเลยครับ
                    </p>
                    <ul class="space-y-2 mb-4">
                        <li>`+` สำหรับการบวก</li>
                        <li>`-` สำหรับการลบ</li>
                        <li>`*` สำหรับการคูณ (เราใช้เครื่องหมายดอกจันนะครับ)</li>
                        <li>`/` สำหรับการหาร</li>
                        <li><strong class="keyword-glossary" data-term="%" data-def="เรียกว่า 'มอดุโล' (Modulo) เป็นการหารเอา 'เศษ' เช่น 7 % 3 จะได้ผลลัพธ์เป็น 1 เพราะ 7 หาร 3 ได้ 2 เหลือเศษ 1">`%`</strong> สำหรับการหารเอา **เศษ** (Modulo) ซึ่งมีประโยชน์มากในการเขียนโปรแกรมครับ</li>
                    </ul>

                    <h3 class="text-xl font-semibold mt-8 mb-3">มาสร้างเครื่องบวกเลขอย่างง่ายกัน!</h3>
                    <p class="text-slate-600 mb-4">
                        โปรแกรมนี้จะถามตัวเลขจากเรา 2 ตัว แล้วนำมาบวกกันและแสดงผลลัพธ์ สังเกตว่าเราจะใช้ฟังก์ชัน <strong class="keyword-glossary" data-term="get_int" data-def="ฟังก์ชันจากไลบรารี cs50.h ใช้สำหรับรับข้อมูลประเภทเลขจำนวนเต็ม (int) จากผู้ใช้โดยเฉพาะ">get_int()</strong> และใช้ <strong class="keyword-glossary code-placeholder" data-term="%i" data-def="Format Specifier สำหรับตัวแปรชนิด Integer (จำนวนเต็ม) เพื่อบอกให้ printf นำค่าตัวเลขจำนวนเต็มมาแสดงผล ณ ตำแหน่งนี้">`%i`</strong> ใน `printf` เพื่อแสดงผลตัวเลขครับ
                    </p>
                    <div class="code-block">
                        <div><span class="code-comment">// หยิบกล่องเครื่องมือที่จำเป็นมาเหมือนเดิม</span></div>
                        <div>
                            <span class="keyword-glossary" data-term="#include" data-def="คำสั่ง 'พรีโปรเซสเซอร์' ใช้บอกคอมไพเลอร์ว่า 'ช่วยไปเอาโค้ดจากไฟล์อื่นมารวมกับไฟล์นี้ที' เหมือนการไปหยิบกล่องเครื่องมือมาเตรียมไว้ใช้งาน">#include</span>
                            <span class="code-string"> &lt;<span class="keyword-glossary" data-term="cs50.h" data-def="ไลบรารี (กล่องเครื่องมือ) พิเศษของ CS50 ที่มีฟังก์ชันอำนวยความสะดวก เช่น get_string(), get_int() ทำให้การรับข้อมูลจากผู้ใช้ทำได้ง่ายขึ้นมาก">cs50.h</span>&gt;</span>
                        </div>
                         <div>
                            <span class="keyword-glossary" data-term="#include" data-def="คำสั่ง 'พรีโปรเซสเซอร์' ใช้บอกคอมไพเลอร์ว่า 'ช่วยไปเอาโค้ดจากไฟล์อื่นมารวมกับไฟล์นี้ที' เหมือนการไปหยิบกล่องเครื่องมือมาเตรียมไว้ใช้งาน">#include</span>
                            <span class="code-string"> &lt;<span class="keyword-glossary" data-term="stdio.h" data-def="ชื่อของ 'กล่องเครื่องมือ' มาตรฐาน (Standard Input/Output Header) ที่มีฟังก์ชันพื้นฐานอย่าง printf() อยู่ข้างใน">stdio.h</span>&gt;</span>
                        </div>
                        <div>&nbsp;</div>
                        <div>
                            <span class="keyword-glossary" data-term="int" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' (Integer)">int</span>
                            <span class="keyword-glossary code-function" data-term="main" data-def="คือชื่อฟังก์ชันที่พิเศษที่สุด ถือเป็น 'ประตูทางเข้าหลัก' ของทุกโปรแกรมในภาษา C">main</span>
                            (<span class="keyword-glossary" data-term="void" data-def="แปลว่า 'ว่างเปล่า' ในที่นี้หมายความว่าฟังก์ชัน main ไม่ต้องการรับข้อมูลใดๆ จากภายนอกเพื่อเริ่มทำงาน">void</span>)
                        </div>
                        <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด">{</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// 1. รับค่าเลขจำนวนเต็มตัวแรกจากผู้ใช้ แล้วเก็บในกล่องชื่อ x</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary" data-term="int" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' (Integer)">int</span>
                            x = 
                            <span class="keyword-glossary code-function" data-term="get_int" data-def="ฟังก์ชันจากไลบรารี cs50.h ใช้สำหรับรับข้อมูลประเภทเลขจำนวนเต็ม (int) จากผู้ใช้โดยเฉพาะ">get_int</span>
                            (<span class="code-string">"x: "</span>);
                        </div>
                         <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// 2. รับค่าเลขจำนวนเต็มตัวที่สองจากผู้ใช้ แล้วเก็บในกล่องชื่อ y</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary" data-term="int" data-def="ชนิดข้อมูลสำหรับเก็บ 'เลขจำนวนเต็ม' (Integer)">int</span>
                            y = 
                            <span class="keyword-glossary code-function" data-term="get_int" data-def="ฟังก์ชันจากไลบรารี cs50.h ใช้สำหรับรับข้อมูลประเภทเลขจำนวนเต็ม (int) จากผู้ใช้โดยเฉพาะ">get_int</span>
                            (<span class="code-string">"y: "</span>);
                        </div>
                        <div>&nbsp;</div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;<span class="code-comment">// 3. นำค่าในกล่อง x และ y มาบวกกัน แล้วแสดงผลลัพธ์</span></div>
                        <div>&nbsp;&nbsp;&nbsp;&nbsp;
                            <span class="keyword-glossary code-function" data-term="printf" data-def="ฟังก์ชันสำหรับแสดงผลข้อความหรือค่าของตัวแปรออกไปยังหน้าจอ">printf</span>
                            (<span class="code-string">"The sum is <span class="keyword-glossary code-placeholder" data-term="%i" data-def="Format Specifier สำหรับตัวแปรชนิด Integer (จำนวนเต็ม) เพื่อบอกให้ printf นำค่าตัวเลขจำนวนเต็มมาแสดงผล ณ ตำแหน่งนี้">%i</span>\n"</span>, x + y);
                        </div>
                         <div><span class="keyword-glossary" data-term="{ }" data-def="ปีกกา คือสัญลักษณ์ที่ใช้กำหนด 'ขอบเขต' การทำงานของฟังก์ชัน หรือบล็อกของโค้ด">}</span></div>
                    </div>
                     <p class="mt-6 text-center text-lg text-slate-700 font-medium">เพียงเท่านี้ คุณก็ได้สร้างโปรแกรมที่ไม่ได้แค่โต้ตอบ แต่ยัง "คิด" และคำนวณให้คุณได้แล้ว!</p>
                </div>
            </section>

        </main>
    </div>

    <div id="glossary-modal-backdrop"></div>
    <div id="glossary-modal">
        <h3 id="glossary-term" class="text-2xl font-bold text-sky-700 mb-2"></h3>
        <p id="glossary-def" class="text-slate-600 leading-relaxed"></p>
        <button id="glossary-close-btn" class="mt-6 bg-slate-200 text-slate-800 px-4 py-2 rounded hover:bg-slate-300 w-full">ปิด</button>
    </div>


<script>
document.addEventListener('DOMContentLoaded', function () {
    // Glossary Modal Logic
    const glossaryModal = document.getElementById('glossary-modal');
    const glossaryBackdrop = document.getElementById('glossary-modal-backdrop');
    document.body.addEventListener('click', function(event) {
        if (event.target.classList.contains('keyword-glossary')) {
            const term = event.target.dataset.term;
            const def = event.target.dataset.def;
            document.getElementById('glossary-term').textContent = term;
            document.getElementById('glossary-def').textContent = def;
            glossaryModal.style.display = 'block';
            glossaryBackdrop.style.display = 'block';
        }
    });
    function closeModal() {
        glossaryModal.style.display = 'none';
        glossaryBackdrop.style.display = 'none';
    }
    document.getElementById('glossary-close-btn').addEventListener('click', closeModal);
    glossaryBackdrop.addEventListener('click', closeModal);
});
</script>

</body>
</html>
