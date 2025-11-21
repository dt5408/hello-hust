[index.html](https://github.com/user-attachments/files/23671268/index.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>华中科技大学 - 校园指南</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        hustBlue: '#003DA5',      // 华科主色-深蓝
                        hustLightBlue: '#1E50B3', // 华科辅助色-浅蓝
                        hustGray: '#F0F2F5',      // 背景灰
                        hustDarkGray: '#333333',  // 文字深灰
                        cardBg: '#f8f9fa',        // 卡片背景色
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .text-shadow {
                text-shadow: 0 2px 4px rgba(0,0,0,0.3);
            }
            .page-transition {
                transition: opacity 0.5s ease, transform 0.5s ease;
            }
            .page-hidden {
                opacity: 0;
                transform: translateY(20px);
                display: none;
            }
            .page-visible {
                opacity: 1;
                transform: translateY(0);
                display: block;
            }
            .index-card {
                transition: all 0.3s ease;
            }
            .index-card:hover {
                transform: translateY(-10px);
                box-shadow: 0 15px 30px rgba(0,0,0,0.1);
            }
            .bg-gradient-hust {
                background: linear-gradient(135deg, var(--tw-gradient-stops));
            }
            .icon-container {
                display: flex;
                align-items: center;
                justify-content: center;
                background: rgba(255,255,255,0.9);
                border-radius: 8px;
            }
        }
    </style>
</head>
<body class="font-sans bg-gray-50 text-hustDarkGray">
<!-- 导航栏 -->
<nav id="navbar" class="fixed w-full bg-white/95 shadow-md z-50 transition-all duration-300">
    <div class="container mx-auto px-4 py-3 flex items-center justify-between">
        <div class="flex items-center">
            <!-- 内置SVG校徽（无需外部图片） -->
            <div class="h-10 w-10 mr-3 flex items-center justify-center bg-hustBlue rounded-full">
                <span class="text-white font-bold text-lg">华科</span>
            </div>
            <h1 class="text-xl md:text-2xl font-bold text-hustBlue">华中科技大学</h1>
        </div>

        <!-- 桌面导航 -->
        <div class="hidden md:flex space-x-6">
            <a href="#" class="nav-link text-hustBlue font-medium hover:text-hustLightBlue transition-colors border-b-2 border-hustBlue py-1" data-page="index">首页</a>
            <a href="#" class="nav-link text-gray-600 font-medium hover:text-hustBlue transition-colors border-b-2 border-transparent hover:border-hustBlue py-1" data-page="library">图书馆</a>
            <a href="#" class="nav-link text-gray-600 font-medium hover:text-hustBlue transition-colors border-b-2 border-transparent hover:border-hustBlue py-1" data-page="dormitory">宿舍</a>
            <a href="#" class="nav-link text-gray-600 font-medium hover:text-hustBlue transition-colors border-b-2 border-transparent hover:border-hustBlue py-1" data-page="classrooms">教学楼</a>
            <a href="#" class="nav-link text-gray-600 font-medium hover:text-hustBlue transition-colors border-b-2 border-transparent hover:border-hustBlue py-1" data-page="playground">操场</a>
            <a href="#" class="nav-link text-gray-600 font-medium hover:text-hustBlue transition-colors border-b-2 border-transparent hover:border-hustBlue py-1" data-page="achievements">成就</a>
        </div>

        <!-- 移动端菜单按钮 -->
        <button id="menuBtn" class="md:hidden text-hustBlue text-2xl">
            <i class="fa fa-bars"></i>
        </button>
    </div>

    <!-- 移动端导航菜单 -->
    <div id="mobileMenu" class="md:hidden hidden bg-white border-t">
        <div class="container mx-auto px-4 py-2 flex flex-col space-y-3">
            <a href="#" class="py-2 text-hustBlue font-medium border-l-4 border-hustBlue pl-2" data-page="index">首页</a>
            <a href="#" class="py-2 text-gray-600 font-medium border-l-4 border-transparent hover:border-hustBlue hover:text-hustBlue pl-2 transition-colors" data-page="library">图书馆</a>
            <a href="#" class="py-2 text-gray-600 font-medium border-l-4 border-transparent hover:border-hustBlue hover:text-hustBlue pl-2 transition-colors" data-page="dormitory">宿舍</a>
            <a href="#" class="py-2 text-gray-600 font-medium border-l-4 border-transparent hover:border-hustBlue hover:text-hustBlue pl-2 transition-colors" data-page="classrooms">教学楼</a>
            <a href="#" class="py-2 text-gray-600 font-medium border-l-4 border-transparent hover:border-hustBlue hover:text-hustBlue pl-2 transition-colors" data-page="playground">操场</a>
            <a href="#" class="py-2 text-gray-600 font-medium border-l-4 border-transparent hover:border-hustBlue hover:text-hustBlue pl-2 transition-colors" data-page="achievements">成就</a>
        </div>
    </div>
</nav>

<!-- 所有页面容器 -->
<div class="pages-container pt-16">
    <!-- 索引页面 - 默认显示 -->
    <div id="index" class="page page-visible page-transition min-h-[calc(100vh-4rem)] flex flex-col">
        <header class="relative h-[50vh] min-h-[300px] flex items-center justify-center overflow-hidden bg-gradient-hust from-hustBlue to-hustLightBlue">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学 校园指南</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">探索校园的每一个角落</p>
            </div>
            <!-- 装饰性SVG元素（内置，无外部依赖） -->
            <div class="absolute bottom-0 left-0 right-0 h-16 bg-gradient-to-t from-gray-50 to-transparent"></div>
            <div class="absolute top-10 left-10 w-20 h-20 opacity-20">
                <i class="fa fa-university text-white text-5xl"></i>
            </div>
            <div class="absolute bottom-10 right-10 w-20 h-20 opacity-20">
                <i class="fa fa-graduation-cap text-white text-5xl"></i>
            </div>
        </header>

        <main class="container mx-auto px-4 py-12 flex-grow">
            <h2 class="text-3xl font-bold text-hustBlue mb-10 text-center">校园地点索引</h2>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 图书馆索引卡片 -->
                <div class="index-card bg-white rounded-xl overflow-hidden shadow-lg" data-page="library">
                    <div class="h-48 overflow-hidden bg-gradient-to-r from-blue-100 to-blue-200 flex items-center justify-center">
                        <div class="icon-container w-32 h-32">
                            <i class="fa fa-book text-hustBlue text-6xl"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="text-hustBlue text-2xl mb-3">
                            <i class="fa fa-book"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">图书馆</h3>
                        <p class="text-gray-600 mb-4">知识的殿堂，学术的港湾，拥有丰富的文献资源和现代化的设施</p>
                        <a href="#" class="inline-block text-hustBlue font-medium hover:text-hustLightBlue transition-colors">
                            了解更多 <i class="fa fa-arrow-right ml-1"></i>
                        </a>
                    </div>
                </div>

                <!-- 宿舍索引卡片 -->
                <div class="index-card bg-white rounded-xl overflow-hidden shadow-lg" data-page="dormitory">
                    <div class="h-48 overflow-hidden bg-gradient-to-r from-green-100 to-green-200 flex items-center justify-center">
                        <div class="icon-container w-32 h-32">
                            <i class="fa fa-home text-green-700 text-6xl"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="text-green-700 text-2xl mb-3">
                            <i class="fa fa-home"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">宿舍</h3>
                        <p class="text-gray-600 mb-4">温馨舒适的校园家园，配备完善的生活设施和便利的服务</p>
                        <a href="#" class="inline-block text-green-700 font-medium hover:text-green-900 transition-colors">
                            了解更多 <i class="fa fa-arrow-right ml-1"></i>
                        </a>
                    </div>
                </div>

                <!-- 教学楼索引卡片 -->
                <div class="index-card bg-white rounded-xl overflow-hidden shadow-lg" data-page="classrooms">
                    <div class="h-48 overflow-hidden bg-gradient-to-r from-purple-100 to-purple-200 flex items-center justify-center">
                        <div class="icon-container w-32 h-32">
                            <i class="fa fa-building text-purple-700 text-6xl"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="text-purple-700 text-2xl mb-3">
                            <i class="fa fa-building"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">教学楼</h3>
                        <p class="text-gray-600 mb-4">知识传授的重要场所，配备现代化的教学设施和先进设备</p>
                        <a href="#" class="inline-block text-purple-700 font-medium hover:text-purple-900 transition-colors">
                            了解更多 <i class="fa fa-arrow-right ml-1"></i>
                        </a>
                    </div>
                </div>

                <!-- 操场索引卡片 -->
                <div class="index-card bg-white rounded-xl overflow-hidden shadow-lg" data-page="playground">
                    <div class="h-48 overflow-hidden bg-gradient-to-r from-orange-100 to-orange-200 flex items-center justify-center">
                        <div class="icon-container w-32 h-32">
                            <i class="fa fa-futbol-o text-orange-700 text-6xl"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="text-orange-700 text-2xl mb-3">
                            <i class="fa fa-futbol-o"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">操场</h3>
                        <p class="text-gray-600 mb-4">运动健身的理想场所，各类体育设施齐全，满足多样化需求</p>
                        <a href="#" class="inline-block text-orange-700 font-medium hover:text-orange-900 transition-colors">
                            了解更多 <i class="fa fa-arrow-right ml-1"></i>
                        </a>
                    </div>
                </div>

                <!-- 成就索引卡片 -->
                <div class="index-card bg-white rounded-xl overflow-hidden shadow-lg" data-page="achievements">
                    <div class="h-48 overflow-hidden bg-gradient-to-r from-yellow-100 to-yellow-200 flex items-center justify-center">
                        <div class="icon-container w-32 h-32">
                            <i class="fa fa-trophy text-yellow-600 text-6xl"></i>
                        </div>
                    </div>
                    <div class="p-6">
                        <div class="text-yellow-600 text-2xl mb-3">
                            <i class="fa fa-trophy"></i>
                        </div>
                        <h3 class="text-xl font-bold mb-2">学校成就</h3>
                        <p class="text-gray-600 mb-4">创新引领，追求卓越，在教学科研领域取得的辉煌成就</p>
                        <a href="#" class="inline-block text-yellow-600 font-medium hover:text-yellow-800 transition-colors">
                            了解更多 <i class="fa fa-arrow-right ml-1"></i>
                        </a>
                    </div>
                </div>
            </div>
        </main>
    </div>

    <!-- 图书馆页面 -->
    <div id="library" class="page page-hidden page-transition">
        <!-- 主横幅 -->
        <header class="relative h-[60vh] min-h-[400px] flex items-center justify-center overflow-hidden bg-gradient-to-r from-hustBlue to-hustLightBlue">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学图书馆</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">知识的殿堂，学术的港湾</p>
            </div>
            <!-- 装饰性图标 -->
            <div class="absolute top-1/4 left-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-book text-white text-8xl"></i>
            </div>
            <div class="absolute bottom-1/4 right-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-bookmark text-white text-8xl"></i>
            </div>
        </header>

        <!-- 主要内容 -->
        <main class="container mx-auto px-4 py-12">
            <section class="mb-16">
                <div class="flex flex-col md:flex-row gap-8 items-center">
                    <div class="md:w-1/2">
                        <h2 class="text-3xl font-bold text-hustBlue mb-4">图书馆概况</h2>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            华中科技大学图书馆是中国高校中规模最大的图书馆之一，由主馆、医学馆、东区分馆和韵苑分馆组成，总面积达6.3万平方米，阅览座位约6000个。
                        </p>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            图书馆馆藏丰富，拥有各类文献资源超过800万册，涵盖了自然科学、工程技术、社会科学、人文科学等各个领域，为师生提供了充足的知识资源。
                        </p>
                        <p class="text-gray-700 leading-relaxed">
                            作为学术信息中心，图书馆不仅提供传统的文献借阅服务，还开展参考咨询、情报分析、学科服务等深层次信息服务，支持学校的教学科研和人才培养。
                        </p>
                    </div>
                    <div class="md:w-1/2 rounded-lg overflow-hidden shadow-xl transform hover:scale-[1.02] transition-all duration-300">
                        <!-- 内置SVG替代图片 -->
                        <div class="w-full h-80 bg-gradient-to-br from-blue-100 to-blue-200 flex flex-col items-center justify-center p-8">
                            <i class="fa fa-university text-hustBlue text-8xl mb-4"></i>
                            <p class="text-hustBlue font-medium text-center">华中科技大学图书馆</p>
                            <p class="text-gray-600 text-sm text-center mt-2">馆藏丰富 · 环境优美 · 服务完善</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-16 bg-hustGray rounded-xl p-8">
                <h2 class="text-3xl font-bold text-hustBlue mb-6 text-center">特色服务</h2>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-hustBlue text-3xl mb-4">
                            <i class="fa fa-laptop"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">数字资源</h3>
                        <p class="text-gray-700">
                            拥有丰富的电子资源，包括中外文数据库、电子期刊、电子图书等，提供24小时在线访问服务，满足师生随时随地的学习研究需求。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-hustBlue text-3xl mb-4">
                            <i class="fa fa-users"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">学习空间</h3>
                        <p class="text-gray-700">
                            设有多种类型的学习空间，包括安静阅览区、讨论室、研究厢、多媒体学习室等，满足不同学习场景和群体的需求。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-hustBlue text-3xl mb-4">
                            <i class="fa fa-book"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">学科服务</h3>
                        <p class="text-gray-700">
                            为各学科提供嵌入式学科服务，包括资源推介、文献传递、科技查新、论文收录引用证明等，助力学科建设和科研创新。
                        </p>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <!-- 宿舍页面 -->
    <div id="dormitory" class="page page-hidden page-transition">
        <header class="relative h-[60vh] min-h-[400px] flex items-center justify-center overflow-hidden bg-gradient-to-r from-green-600 to-green-800">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学宿舍</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">温馨舒适的校园家园</p>
            </div>
            <!-- 装饰性图标 -->
            <div class="absolute top-1/4 left-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-bed text-white text-8xl"></i>
            </div>
            <div class="absolute bottom-1/4 right-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-shower text-white text-8xl"></i>
            </div>
        </header>

        <main class="container mx-auto px-4 py-12">
            <section class="mb-16">
                <div class="flex flex-col md:flex-row-reverse gap-8 items-center">
                    <div class="md:w-1/2">
                        <h2 class="text-3xl font-bold text-green-700 mb-4">宿舍概况</h2>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            华中科技大学宿舍分布在多个区域，包括韵苑、紫菘、沁苑、启明等宿舍群，总建筑面积达50余万平方米，为学生提供舒适的居住环境。
                        </p>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            宿舍以4-6人间为主，配备有空调、热水系统、独立卫生间等现代化设施，部分宿舍还配有独立阳台和衣柜，满足学生的日常生活需求。
                        </p>
                        <p class="text-gray-700 leading-relaxed">
                            每个宿舍区都设有学生活动中心、自习室、洗衣房、超市等配套设施，为学生提供便利的生活服务，营造温馨和谐的社区氛围。
                        </p>
                    </div>
                    <div class="md:w-1/2 rounded-lg overflow-hidden shadow-xl transform hover:scale-[1.02] transition-all duration-300">
                        <!-- 内置SVG替代图片 -->
                        <div class="w-full h-80 bg-gradient-to-br from-green-100 to-green-200 flex flex-col items-center justify-center p-8">
                            <i class="fa fa-home text-green-700 text-8xl mb-4"></i>
                            <p class="text-green-700 font-medium text-center">华科学生宿舍</p>
                            <p class="text-gray-600 text-sm text-center mt-2">空调热水 · 独立卫浴 · 配套齐全</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-16">
                <h2 class="text-3xl font-bold text-green-700 mb-6 text-center">宿舍区域</h2>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <div class="group bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="h-48 bg-gradient-to-r from-green-100 to-green-200 flex items-center justify-center relative">
                            <i class="fa fa-building-o text-green-700 text-7xl"></i>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-end">
                                <p class="text-white p-4 text-lg">韵苑宿舍区位于东校区，毗邻青年园</p>
                            </div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-green-700 mb-2">韵苑宿舍群</h3>
                            <p class="text-gray-700">主要为东校区本科生居住，周边配套设施完善，靠近韵苑食堂、篮球场和教学楼，生活便利。</p>
                        </div>
                    </div>

                    <div class="group bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="h-48 bg-gradient-to-r from-green-100 to-green-200 flex items-center justify-center relative">
                            <i class="fa fa-building text-green-700 text-7xl"></i>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-end">
                                <p class="text-white p-4 text-lg">紫菘宿舍区环境优美，生活氛围浓厚</p>
                            </div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-green-700 mb-2">紫菘宿舍群</h3>
                            <p class="text-gray-700">位于主校区西部，是学校历史较久的宿舍区之一，周边绿树成荫，靠近图书馆和西操。</p>
                        </div>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <!-- 教学楼页面 -->
    <div id="classrooms" class="page page-hidden page-transition">
        <header class="relative h-[60vh] min-h-[400px] flex items-center justify-center overflow-hidden bg-gradient-to-r from-purple-600 to-purple-800">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学教学楼</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">知识传授的重要场所</p>
            </div>
            <!-- 装饰性图标 -->
            <div class="absolute top-1/4 left-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-blackboard text-white text-8xl"></i>
            </div>
            <div class="absolute bottom-1/4 right-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-pencil text-white text-8xl"></i>
            </div>
        </header>

        <main class="container mx-auto px-4 py-12">
            <section class="mb-16">
                <div class="flex flex-col md:flex-row gap-8 items-center">
                    <div class="md:w-1/2">
                        <h2 class="text-3xl font-bold text-purple-700 mb-4">教学楼概况</h2>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            华中科技大学校园广阔，教学楼分布合理，主要包括主校区的一号楼至三十号楼、东校区的韵苑教学楼群、西校区的同济医学院教学楼群等。
                        </p>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            教学楼配备了现代化的教学设施，包括多媒体教室、智慧教室、实验室、阶梯教室等，满足不同学科的教学需求，为师生提供良好的教学环境。
                        </p>
                        <p class="text-gray-700 leading-relaxed">
                            各教学楼之间有便捷的交通连接，校园内公交线路覆盖主要教学区，方便师生在不同教学楼之间往来。
                        </p>
                    </div>
                    <div class="md:w-1/2 rounded-lg overflow-hidden shadow-xl transform hover:scale-[1.02] transition-all duration-300">
                        <!-- 内置SVG替代图片 -->
                        <div class="w-full h-80 bg-gradient-to-br from-purple-100 to-purple-200 flex flex-col items-center justify-center p-8">
                            <i class="fa fa-building text-purple-700 text-8xl mb-4"></i>
                            <p class="text-purple-700 font-medium text-center">华科教学楼群</p>
                            <p class="text-gray-600 text-sm text-center mt-2">智慧教室 · 实验设备 · 交通便利</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-16 bg-hustGray rounded-xl p-8">
                <h2 class="text-3xl font-bold text-purple-700 mb-6 text-center">特色教学楼</h2>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-purple-700 text-3xl mb-4">
                            <i class="fa fa-tree"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">梧桐语林</h3>
                        <p class="text-gray-700">
                            位于主校区中心位置，是学校标志性教学楼之一，以其独特的建筑风格和浓厚的学术氛围闻名，主要承担理工科基础课程教学。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-purple-700 text-3xl mb-4">
                            <i class="fa fa-flask"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">科技楼</h3>
                        <p class="text-gray-700">
                            配备了先进的实验室和科研设备，是学校科研活动的重要场所，也是研究生开展科研工作的主要基地。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-purple-700 text-3xl mb-4">
                            <i class="fa fa-university"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">人文楼</h3>
                        <p class="text-gray-700">
                            主要承担人文社会科学类课程教学，楼内设有多个研讨室和学术报告厅，经常举办各类学术讲座和文化活动。
                        </p>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <!-- 操场页面 -->
    <div id="playground" class="page page-hidden page-transition">
        <header class="relative h-[60vh] min-h-[400px] flex items-center justify-center overflow-hidden bg-gradient-to-r from-orange-500 to-orange-700">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学操场</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">运动健身的理想场所</p>
            </div>
            <!-- 装饰性图标 -->
            <div class="absolute top-1/4 left-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-running text-white text-8xl"></i>
            </div>
            <div class="absolute bottom-1/4 right-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-basketball-ball text-white text-8xl"></i>
            </div>
        </header>

        <main class="container mx-auto px-4 py-12">
            <section class="mb-16">
                <div class="flex flex-col md:flex-row gap-8 items-center">
                    <div class="md:w-1/2">
                        <h2 class="text-3xl font-bold text-orange-700 mb-4">运动设施概况</h2>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            华中科技大学拥有完善的体育设施，包括多个标准化操场、体育馆、篮球场、足球场、网球场、游泳馆等，总面积达15万平方米以上。
                        </p>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            学校重视学生体育锻炼，提出"每天锻炼一小时，健康工作五十年，幸福生活一辈子"的体育理念，为师生提供了充足的运动空间和设施。
                        </p>
                        <p class="text-gray-700 leading-relaxed">
                            各个校区都分布有相应的运动设施，方便不同区域的师生就近锻炼，定期举办各类体育赛事和活动，营造了良好的体育文化氛围。
                        </p>
                    </div>
                    <div class="md:w-1/2 rounded-lg overflow-hidden shadow-xl transform hover:scale-[1.02] transition-all duration-300">
                        <!-- 内置SVG替代图片 -->
                        <div class="w-full h-80 bg-gradient-to-br from-orange-100 to-orange-200 flex flex-col items-center justify-center p-8">
                            <i class="fa fa-futbol-o text-orange-700 text-8xl mb-4"></i>
                            <p class="text-orange-700 font-medium text-center">华科体育中心</p>
                            <p class="text-gray-600 text-sm text-center mt-2">标准场地 · 专业设备 · 全天开放</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-16">
                <h2 class="text-3xl font-bold text-orange-700 mb-6 text-center">主要运动场地</h2>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <div class="group bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="h-48 bg-gradient-to-r from-orange-100 to-orange-200 flex items-center justify-center relative">
                            <i class="fa fa-route text-orange-700 text-7xl"></i>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-end">
                                <p class="text-white p-4 text-lg">西边操场是学校最活跃的运动场所之一</p>
                            </div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-orange-700 mb-2">西边操场</h3>
                            <p class="text-gray-700">位于主校区西部，靠近紫菘宿舍区，拥有标准400米塑胶跑道、足球场和看台，是校内大型运动会的举办场地。</p>
                        </div>
                    </div>

                    <div class="group bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="h-48 bg-gradient-to-r from-orange-100 to-orange-200 flex items-center justify-center relative">
                            <i class="fa fa-basketball-ball text-orange-700 text-7xl"></i>
                            <div class="absolute inset-0 bg-gradient-to-t from-black/20 to-transparent opacity-0 group-hover:opacity-100 transition-all duration-300 flex items-end">
                                <p class="text-white p-4 text-lg">东边体育馆设施先进，功能齐全</p>
                            </div>
                        </div>
                        <div class="p-6">
                            <h3 class="text-xl font-semibold text-orange-700 mb-2">东边体育馆</h3>
                            <p class="text-gray-700">位于东校区，内有篮球场、羽毛球场、乒乓球场等多个运动场地，配备了先进的照明和通风系统，可全天候使用。</p>
                        </div>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <!-- 成就页面 -->
    <div id="achievements" class="page page-hidden page-transition">
        <header class="relative h-[60vh] min-h-[400px] flex items-center justify-center overflow-hidden bg-gradient-to-r from-yellow-500 to-yellow-700">
            <div class="container mx-auto px-4 z-10 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-white mb-4 text-shadow">华中科技大学成就</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-white max-w-3xl mx-auto text-shadow">创新引领，追求卓越</p>
            </div>
            <!-- 装饰性图标 -->
            <div class="absolute top-1/4 left-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-award text-white text-8xl"></i>
            </div>
            <div class="absolute bottom-1/4 right-1/4 w-32 h-32 opacity-10">
                <i class="fa fa-star text-white text-8xl"></i>
            </div>
        </header>

        <main class="container mx-auto px-4 py-12">
            <section class="mb-16">
                <div class="flex flex-col md:flex-row gap-8 items-center">
                    <div class="md:w-1/2">
                        <h2 class="text-3xl font-bold text-yellow-600 mb-4">学校成就概况</h2>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            华中科技大学是国家"双一流"建设高校、"985工程"和"211工程"重点建设高校，在人才培养、科学研究、社会服务等方面取得了显著成就。
                        </p>
                        <p class="text-gray-700 mb-4 leading-relaxed">
                            学校在多个学科领域处于国内领先水平，尤其在机械工程、光学工程、生物医学工程、计算机科学与技术等学科领域具有重要影响力。
                        </p>
                        <p class="text-gray-700 leading-relaxed">
                            建校以来，学校为国家培养了大批优秀人才，包括院士、企业家、政府官员等各界精英，为国家和社会发展做出了重要贡献。
                        </p>
                    </div>
                    <div class="md:w-1/2 rounded-lg overflow-hidden shadow-xl transform hover:scale-[1.02] transition-all duration-300">
                        <!-- 内置SVG替代图片 -->
                        <div class="w-full h-80 bg-gradient-to-br from-yellow-100 to-yellow-200 flex flex-col items-center justify-center p-8">
                            <i class="fa fa-trophy text-yellow-600 text-8xl mb-4"></i>
                            <p class="text-yellow-600 font-medium text-center">华科辉煌成就</p>
                            <p class="text-gray-600 text-sm text-center mt-2">双一流高校 · 科研强校 · 人才摇篮</p>
                        </div>
                    </div>
                </div>
            </section>

            <section class="mb-16 bg-hustGray rounded-xl p-8">
                <h2 class="text-3xl font-bold text-yellow-600 mb-6 text-center">科研与学术成就</h2>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-yellow-600 text-3xl mb-4">
                            <i class="fa fa-trophy"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">科研成果</h3>
                        <p class="text-gray-700">
                            学校科研实力雄厚，近年来获得国家自然科学奖、国家技术发明奖、国家科技进步奖等国家级奖项50余项，在多个领域取得重大突破。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-yellow-600 text-3xl mb-4">
                            <i class="fa fa-flask"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">科研平台</h3>
                        <p class="text-gray-700">
                            拥有国家重点实验室5个、国家工程研究中心7个、国家工程技术研究中心1个，以及一批省部级科研基地，为科研创新提供了有力支撑。
                        </p>
                    </div>

                    <div class="bg-white rounded-lg p-6 shadow-md hover:shadow-lg transition-all duration-300">
                        <div class="text-yellow-600 text-3xl mb-4">
                            <i class="fa fa-book"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-2">学术影响</h3>
                        <p class="text-gray-700">
                            学校在国内外学术期刊发表论文数量和质量均位居全国高校前列，拥有一批具有重要国际影响力的学术带头人。
                        </p>
                    </div>
                </div>
            </section>
        </main>
    </div>
</div>

<!-- 页脚 -->
<footer class="bg-hustBlue text-white py-10">
    <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-8">
            <div>
                <h3 class="text-xl font-semibold mb-4">华中科技大学</h3>
                <p class="mb-4">湖北省武汉市洪山区珞喻路1037号</p>
                <p>邮编：430074</p>
            </div>
            <div>
                <h3 class="text-xl font-semibold mb-4">快速链接</h3>
                <ul class="space-y-2">
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="index">首页</a></li>
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="library">图书馆</a></li>
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="dormitory">宿舍</a></li>
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="classrooms">教学楼</a></li>
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="playground">操场</a></li>
                    <li><a href="#" class="hover:text-gray-200 transition-colors" data-page="achievements">成就</a></li>
                </ul>
            </div>
            <div>
                <h3 class="text-xl font-semibold mb-4">联系我们</h3>
                <div class="flex items-center mb-2">
                    <i class="fa fa-phone mr-2"></i>
                    <span>027-87542114</span>
                </div>
                <div class="flex items-center mb-2">
                    <i class="fa fa-envelope mr-2"></i>
                    <span>info@hust.edu.cn</span>
                </div>
                <div class="flex space-x-4 mt-4">
                    <a href="#" class="text-white hover:text-gray-200 transition-colors"><i class="fa fa-weibo text-xl"></i></a>
                    <a href="#" class="text-white hover:text-gray-200 transition-colors"><i class="fa fa-wechat text-xl"></i></a>
                    <a href="#" class="text-white hover:text-gray-200 transition-colors"><i class="fa fa-youtube-play text-xl"></i></a>
                </div>
            </div>
        </div>
        <div class="border-t border-white/20 pt-6 text-center text-sm">
            <p>© 2025 华中科技大学 版权所有 | 小组作业专用</p>
        </div>
    </div>
</footer>

<script>
        // 页面切换功能
        document.addEventListener('DOMContentLoaded', function() {
            // 移动端菜单切换
            const menuBtn = document.getElementById('menuBtn');
            const mobileMenu = document.getElementById('mobileMenu');

            menuBtn.addEventListener('click', function() {
                mobileMenu.classList.toggle('hidden');
            });

            // 索引卡片点击事件
            const indexCards = document.querySelectorAll('.index-card');
            indexCards.forEach(card => {
                card.addEventListener('click', function() {
                    const targetPageId = this.getAttribute('data-page');
                    if (targetPageId) {
                        document.querySelector(`.nav-link[data-page="${targetPageId}"]`).click();
                    }
                });
            });

            // 导航链接点击事件
            const navLinks = document.querySelectorAll('.nav-link, footer a[data-page]');

            navLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();

                    // 获取目标页面ID
                    const targetPageId = this.getAttribute('data-page');
                    if (!targetPageId) return;

                    // 隐藏所有页面
                    document.querySelectorAll('.page').forEach(page => {
                        page.classList.remove('page-visible');
                        page.classList.add('page-hidden');
                    });

                    // 显示目标页面
                    const targetPage = document.getElementById(targetPageId);
                    if (targetPage) {
                        targetPage.classList.remove('page-hidden');
                        // 触发重排后添加可见类以启用过渡动画
                        setTimeout(() => {
                            targetPage.classList.add('page-visible');
                        }, 50);
                    }

                    // 更新导航链接样式
                    navLinks.forEach(l => {
                        l.classList.remove('text-hustBlue', 'border-hustBlue');
                        l.classList.add('text-gray-600', 'border-transparent');
                    });

                    this.classList.remove('text-gray-600', 'border-transparent');
                    this.classList.add('text-hustBlue', 'border-hustBlue');

                    // 关闭移动菜单
                    mobileMenu.classList.add('hidden');

                    // 滚动到页面顶部
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                });
            });

            // 滚动时导航栏样式变化
            window.addEventListener('scroll', function() {
                const navbar = document.getElementById('navbar');
                if (window.scrollY > 50) {
                    navbar.classList.add('py-2', 'shadow-lg');
                    navbar.classList.remove('py-3', 'shadow-md');
                } else {
                    navbar.classList.add('py-3', 'shadow-md');
                    navbar.classList.remove('py-2', 'shadow-lg');
                }
            });
        });
    </script>
</body>
</html>
