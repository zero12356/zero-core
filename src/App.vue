<!-- The exported code uses Tailwind CSS. Install Tailwind CSS in your dev environment to ensure all styles work. -->
<template>
  <div class="min-h-screen bg-black text-white font-sans relative overflow-hidden">
    <!-- 动态背景粒子 -->
    <div class="fixed inset-0 pointer-events-none z-0">
      <div v-for="i in 50" :key="i" class="particle absolute rounded-full bg-green-400 opacity-20" 
           :style="getParticleStyle(i)"></div>
    </div>
    
    <!-- 鼠标跟随粒子光标效果 -->
    <div class="fixed pointer-events-none z-50">
      <!-- 主光标 -->
      <div ref="cursor" class="absolute w-4 h-4 bg-green-400 rounded-full transform -translate-x-1/2 -translate-y-1/2 cursor-glow smooth-cursor"></div>
      
      <!-- 丝滑拖尾粒子 -->
      <div v-for="i in 15" :key="`trail-${i}`" :data-trail="i" 
           class="absolute rounded-full transform -translate-x-1/2 -translate-y-1/2 trail-particle smooth-trail"
           :style="{ 
             width: `${Math.max(12 - i * 0.6, 2)}px`,
             height: `${Math.max(12 - i * 0.6, 2)}px`,
             background: `hsl(${120 + i * 2}, ${90 - i * 3}%, ${70 - i * 2}%)`,
             opacity: Math.max(0.9 - i * 0.06, 0.1),
             filter: `blur(${i * 0.3}px)`,
             zIndex: 50 - i
           }"></div>
      
      <!-- 飘散光斑粒子 -->
      <div v-for="j in 15" :key="`sparkle-${j}`" :data-sparkle="j"
           class="absolute rounded-full transform -translate-x-1/2 -translate-y-1/2 sparkle-particle"
           :style="{
             width: '0.5px',
             height: '0.5px',
             background: '#4ade80',
             opacity: 0,
             filter: 'blur(0.2px)',
             zIndex: 45
           }"></div>
    </div>
    <!-- 封面区域 -->
    <div class="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div
        class="absolute inset-0 bg-cover bg-center"
        :style="{
          backgroundImage:
            'url(https://readdy.ai/api/search-image?query=dark%20futuristic%20technology%20background%20with%20flowing%20green%20neon%20light%20particles%20geometric%20wireframe%20patterns%20digital%20circuit%20lines%20and%20abstract%20cyber%20elements%20creating%20sophisticated%20modern%20atmosphere%20for%20AIGC%20designer%20portfolio&width=1440&height=1024&seq=portfolio-hero-001&orientation=landscape)',
        }"
      ></div>
      <div class="absolute inset-0 bg-black bg-opacity-50"></div>
      <div class="relative z-10 text-center max-w-6xl mx-auto px-8">
        <div class="mb-6">
          <span class="text-sm uppercase tracking-[0.3em] text-green-400 font-light opacity-80"
            >AIGC DESIGNER PORTFOLIO</span
          >
        </div>
        <h1 class="text-7xl md:text-8xl font-bold mb-8 leading-tight">
          <div class="mb-4">Creative Vision</div>
          <div class="text-green-400">Meets Technology</div>
        </h1>
        <div class="mb-12">
          <p class="text-xl text-gray-300 mb-2 font-light">
            Zhu Rui - AIGC Effects Designer & Product Manager
          </p>
          <p class="text-lg text-gray-400 font-light"></p>
        </div>
        <div class="flex justify-center gap-4 mb-16">
          <button
            class="border border-green-400 text-green-400 hover:bg-green-400 hover:text-black px-6 py-2.5 font-medium text-sm transition-all duration-300 transform hover:scale-105 cursor-pointer !rounded-button whitespace-nowrap"
          >
            AIGC 特效落地
          </button>
          <button
            class="border border-green-400 text-green-400 hover:bg-green-400 hover:text-black px-6 py-2.5 font-medium text-sm transition-all duration-300 transform hover:scale-105 cursor-pointer !rounded-button whitespace-nowrap"
          >
            潮流风格创造
          </button>
          <button
            class="border border-green-400 text-green-400 hover:bg-green-400 hover:text-black px-6 py-2.5 font-medium text-sm transition-all duration-300 transform hover:scale-105 cursor-pointer !rounded-button whitespace-nowrap"
          >
            产品化与工程化思维
          </button>
        </div>
        <div class="flex items-center justify-center gap-12">
          <div class="flex items-center gap-3">
            <div class="w-8 h-8 rounded-full bg-green-400 flex items-center justify-center">
              <i class="fas fa-brain text-black text-lg"></i>
            </div>
            <span class="text-gray-300">ENTJ</span>
          </div>
          <div class="flex items-center gap-3">
            <div class="w-8 h-8 rounded-full bg-green-400 flex items-center justify-center">
              <i class="fas fa-phone text-black text-lg"></i>
            </div>
            <span class="text-gray-300">18784308516</span>
          </div>
          <div class="flex items-center gap-3">
            <div class="w-8 h-8 rounded-full bg-green-400 flex items-center justify-center">
              <i class="fab fa-weixin text-black text-lg"></i>
            </div>
            <span class="text-gray-300">Aprilmay_sue</span>
          </div>
        </div>
      </div>
      <!-- 浮动元素 -->
      <div
        class="absolute top-20 left-20 w-20 h-20 border border-green-400 border-opacity-30 rotate-45 animate-pulse"
      ></div>
      <div
        class="absolute top-40 right-32 w-16 h-16 bg-green-400 bg-opacity-20 rounded-full animate-bounce"
      ></div>
      <div
        class="absolute bottom-32 left-40 w-12 h-12 border-2 border-green-500 rotate-12 animate-spin"
        style="animation-duration: 8s"
      ></div>
      <div
        class="absolute bottom-20 right-20 w-24 h-1 bg-gradient-to-r from-green-400 to-transparent"
      ></div>
    </div>
    <!-- 项目展示区域 -->
    <div class="py-20 px-8">
      <div class="max-w-7xl mx-auto">
        <!-- 章节标题 -->
        <div class="text-center mb-16">
          <h2 class="text-5xl font-bold mb-6">
            <span class="text-white">Chapter 1</span>
            <span class="text-green-400"> 爆款制造机：打造病毒式传播特效</span>
          </h2>
          <p class="text-2xl text-gray-400">Crafting Viral Effects for Mass Engagement</p>
        </div>
        <!-- 项目1 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 animate-on-scroll" data-animation="fadeInUp">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 1：</span>人物转绘工作流设计
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              从 MBTI 到韩风，打造可复用的 AI 人物风格化工作流
            </h4>
            <!-- 项目思考 -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
              <div
                class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
              >
                <h6 class="text-xl font-bold mb-4 text-green-400">The Insight</h6>
                <p class="text-gray-300 leading-relaxed">
                  在社交媒体上，用户极度热衷于通过风格化的头像来表达自我身份（如MBTI、星座）。
                </p>
              </div>
              <div
                class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
              >
                <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                <p class="text-gray-300 leading-relaxed">
                  针对性地训练了多款风格LoRA模型，结合Pulid-Flux能高度保留人物面部特征的模型，搭建了这套人物转绘工作流。用户只需上传一张自拍，就能一键生成多种潮流风格的人物头像。
                </p>
              </div>
            </div>
            <!-- ComfyUI节点图展示 -->
            <div class="mb-12">
              <div
                class="bg-black bg-opacity-50 rounded-2xl p-8 border border-green-400 border-opacity-20"
              >
                <h5 class="text-xl font-semibold mb-4 text-green-400">工作流节点展示</h5>
                <div class="overflow-hidden rounded-xl">
                  <img
                    src="https://i.mji.rip/2025/08/04/03b5b29d6495c97a072fabab9ee5763d.png"
                    alt="ComfyUI节点图"
                    class="w-full h-full object-cover cursor-pointer"
                    @click="
                      openImageModal({
                        url: 'https://i.mji.rip/2025/08/04/03b5b29d6495c97a072fabab9ee5763d.png',
                        alt: 'ComfyUI节点图',
                      })
                    "
                  />
                </div>
              </div>
            </div>
            <!-- 风格化效果展示 -->
            <div class="mb-12">
              <h5 class="text-xl font-semibold mb-6 text-white">风格化效果展示</h5>
              <div class="grid grid-cols-1 gap-8">
                <!-- 韩风效果 -->
                <div class="space-y-6">
                  <h6 class="text-lg font-medium text-green-400">韩风风格</h6>
                  <div class="grid grid-cols-2 md:grid-cols-4 gap-6">
                    <div
                      v-for="(img, index) in koreanStyleImages"
                      :key="index"
                      class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 hover:shadow-2xl hover:shadow-green-400/30 transition-all duration-300 transform hover:-translate-y-2"
                    >
                      <img
                        :src="img.url"
                        :alt="img.alt"
                        class="w-full h-full object-cover"
                        @click="openImageModal(img)"
                      />
                    </div>
                  </div>
                </div>
                <!-- 波普卡通风格 -->
                <div class="space-y-6">
                  <h6 class="text-lg font-medium text-green-400">波普卡通风格</h6>
                  <div class="flex justify-center">
                    <div
                      class="rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform"
                    >
                      <img
                        src="https://img.cdn1.vip/i/688e25cfae5cd_1754146255.jpeg"
                        alt="波普卡通风格"
                        class="object-contain"
                        @click="
                          openImageModal({
                            url: 'https://img.cdn1.vip/i/688e25cfae5cd_1754146255.jpeg',
                            alt: '波普卡通风格',
                          })
                        "
                      />
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- 项目详情 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 animate-on-scroll" data-animation="fadeInLeft">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 2：</span>公司周年庆共创活动
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              引爆全员参与：7000+ 人次参与的 AIGC 共创活动设计
            </h4>
            <!-- 作品展示网格 -->
            <div class="mb-12">
              <h5 class="text-xl font-semibold mb-6 text-white"></h5>
              <p class="text-gray-400 mb-8">由员工共创生成的创意海报，兼具多样性和创意性</p>
              <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                                  <div
                    v-for="(poster, index) in posterImages"
                    :key="index"
                    class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 hover:shadow-2xl hover:shadow-green-400/30 transition-all duration-300 transform hover:-translate-y-2 animate-on-scroll"
                    :data-animation="`fadeInUp`"
                    :style="{ animationDelay: `${index * 0.1}s` }"
                    @click="openImageModal(poster)"
                  >
                  <img
                    :src="poster.url"
                    :alt="`创意海报${index + 1}`"
                    class="w-full h-full object-cover"
                  />
                </div>
              </div>
            </div>
            <!-- 工作流展示 -->
            <div class="mb-12">
              <div
                class="bg-black bg-opacity-50 rounded-2xl p-8 border border-green-400 border-opacity-20"
              >
                <h5 class="text-xl font-semibold mb-4 text-green-400">工作流节点展示</h5>
                <div class="overflow-hidden rounded-xl">
                  <img
                    src="https://i.mji.rip/2025/08/05/acb83ff9ea29777be3f118232f2244ed.png"
                    alt="工作流节点截图"
                    class="w-full h-full object-cover cursor-pointer"
                    @click="
                      openImageModal({
                        url: 'https://i.mji.rip/2025/08/05/acb83ff9ea29777be3f118232f2244ed.png',
                        alt: '工作流节点截图',
                      })
                    "
                  />
                </div>
              </div>
            </div>
            <!-- 项目思考 -->
            <div class="space-y-8">
              <h5 class="text-2xl font-semibold text-green-400 mb-6"></h5>
              <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div
                  class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
                >
                  <h6 class="text-xl font-bold mb-4 text-green-400">The Goal</h6>
                  <p class="text-gray-300 leading-relaxed">
                    设计一个足够简单、足够有趣的工作流，让公司里任何岗位的同事（即使没有设计背景）都能轻松参与，用
                    AIGC 生成一张带有公司品牌符号的创意海报，提升周年庆的参与感和归属感。
                  </p>
                </div>
                <div
                  class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
                >
                  <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                  <p class="text-gray-300 leading-relaxed">
                    利用 ControlNet 模型精准控制公司 Logo 的轮廓，同时开放 IPAdapter
                    让用户上传任意图片来影响风格，Prompt
                    则给予用户自由表达的空间。兼顾品牌的一致性和用户的创造性。
                  </p>
                </div>
                <div
                  class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
                >
                  <h6 class="text-xl font-bold mb-4 text-green-400">The Outcome</h6>
                  <p class="text-gray-300 leading-relaxed">
                    活动吸引了全公司员工的广泛参与，累计生成了
                    <span class="text-green-400 font-bold">28,744 张</span>
                    作品，成为了周年庆期间讨论度最高的线上活动。
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- Chapter 2 -->
    <div class="py-20 px-8 bg-gradient-to-br from-black via-gray-900 to-green-900">
      <div class="max-w-7xl mx-auto">
        <!-- 章节标题 -->
        <div class="text-center mb-16">
          <h2 class="text-5xl font-bold mb-6">
            <span class="text-white">Chapter 2</span>
            <span class="text-green-400"> 商业价值转化：让AI为业务和产品赋能</span>
          </h2>
          <p class="text-2xl text-gray-400">AI-Driven Business Value & Product Enhancement</p>
        </div>
        <!-- 项目3 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 animate-on-scroll" data-animation="fadeInRight">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 3：</span>产品卖点图Agent设计
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              从Brief到出图：端到端的AIGC产品卖点图自动化工作流设计
            </h4>
            <!-- 项目思考 -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
              <div
                class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
              >
                <h6 class="text-xl font-bold mb-4 text-green-400">The Goal</h6>
                <p class="text-gray-300 leading-relaxed">
                  传统电商卖点图制作周期长、成本高。我们目标是构建一个自动化流程，让运营人员可以快速、低成本地生成高质量的卖点图。
                </p>
              </div>
              <div
                class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30"
              >
                <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                <p class="text-gray-300 leading-relaxed">
                  将顶尖广告公司的创意Know-how拆解为多个步骤，并将其构建为Agent的思考链。它能自动分析产品卖点（如'轻'），并将其转化为视觉元素（如'羽毛'），最终调用图像生成模型完成构图。
                </p>
              </div>
            </div>
            <!-- 作品展示 -->
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-12">
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30 md:col-span-2 lg:col-span-1"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3fd0803c7_1754152912.jpeg"
                  alt="eufyCam S3 Pro"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3fd0803c7_1754152912.jpeg',
                      alt: 'eufyCam S3 Pro',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">
                    eufyCam S3 Pro 4-Cam Kit + 1 TB Hard Drive homebase
                  </h5>
                  <p class="text-gray-300">
                    融入NAS功能，家庭数据随时上传
                    可以自定义数据存储，摄像头录像自动分类，家庭回忆数据保留更长时间，并且可以自己上传家庭数据
                  </p>
                </div>
              </div>
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3ecea782c_1754152654.jpeg"
                  alt="头戴式耳机-轻盈贴合"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3ecea782c_1754152654.jpeg',
                      alt: '头戴式耳机-轻盈贴合',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">头戴式耳机</h5>
                  <p class="text-gray-300">
                    轻盈贴合 全日舒适，大接触面积零压佩戴感，记忆棉耳罩温柔包裹，自在听音享受
                  </p>
                </div>
              </div>
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3eccaae04_1754152652.jpeg"
                  alt="头戴式耳机-智能降噪"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3eccaae04_1754152652.jpeg',
                      alt: '头戴式耳机-智能降噪',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">头戴式耳机</h5>
                  <p class="text-gray-300">
                    智能降噪 随境而静
                    地铁喧嚣瞬间消散，智能自适应降噪根据环境调整，让你在通勤时沉浸于音乐，专注每一段旅程。
                  </p>
                </div>
              </div>
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3ecd2dfb1_1754152653.jpeg"
                  alt="基站-超大容量"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3ecd2dfb1_1754152653.jpeg',
                      alt: '基站-超大容量',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">基站</h5>
                  <p class="text-gray-300">32T超大容量</p>
                </div>
              </div>
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3ece0e4b5_1754152654.jpeg"
                  alt="Portable Power Station"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3ece0e4b5_1754152654.jpeg',
                      alt: 'Portable Power Station',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">Portable Power Station</h5>
                  <p class="text-gray-300">
                    POWER UP ANYWHERE，This travel-friendly power station is 30% smaller than
                    similar products, so strap up and go anywhere.
                  </p>
                </div>
              </div>
              <div
                class="bg-black bg-opacity-50 rounded-2xl overflow-hidden border border-green-400 border-opacity-30"
              >
                <img
                  src="https://img.cdn1.vip/i/688e3fcb9257f_1754152907.jpeg"
                  alt="蓝牙音箱"
                  class="w-full h-[300px] object-cover cursor-pointer"
                  @click="
                    openImageModal({
                      url: 'https://img.cdn1.vip/i/688e3fcb9257f_1754152907.jpeg',
                      alt: '蓝牙音箱',
                    })
                  "
                />
                <div class="p-6">
                  <h5 class="text-lg font-semibold text-green-400 mb-2">蓝牙音箱</h5>
                  <p class="text-gray-300">防水，重低音，便携，可当作充电宝使用。</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <!-- 项目4 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 animate-on-scroll" data-animation="fadeInUp">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 4：</span>soundcore视频转绘
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              动态视觉探索：为soundcore新品打造多风格AI转绘视频
            </h4>
            
            <!-- 项目思考 -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
              <div class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30">
                <h6 class="text-xl font-bold mb-4 text-green-400">The Goal</h6>
                <p class="text-gray-300 leading-relaxed">
                  为新品的多配色展现探索更具视觉冲击力和成本效益的宣传片制作方式。
                </p>
              </div>
              <div class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30">
                <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                <p class="text-gray-300 leading-relaxed">
                  研究并测试了多种视频转绘技术组合，包括IP-Adapter、风格LoRA、animatediff、Go Enhance等工具方法产出。
                </p>
              </div>
            </div>
            
            <!-- 风格展示区域 -->
            <div class="space-y-16 mb-12">
              <!-- 绿白配色：极简图形风 -->
              <div class="space-y-6">
                <h5 class="text-xl font-semibold text-white">绿白配色：极简图形风</h5>
                <div class="grid grid-cols-1 lg:grid-cols-5 gap-6">
                  <!-- 左侧静态图片区域 -->
                  <div class="lg:col-span-3">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">分镜示意</span>
                    </div>
                    <div class="grid grid-cols-3 gap-3 h-full">
                      <!-- 第一行 -->
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688eeb5a324f6_1754196826.jpeg" alt="绿白风格定调" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688eeb5a324f6_1754196826.jpeg', alt: '绿白风格定调'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5e929f17c_1754160786.jpeg" alt="绿白分镜3" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5e929f17c_1754160786.jpeg', alt: '绿白分镜3'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5e80a510f_1754160768.jpeg" alt="绿白分镜1" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5e80a510f_1754160768.jpeg', alt: '绿白分镜1'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5ea1d0bf6_1754160801.jpeg" alt="绿白分镜4" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5ea1d0bf6_1754160801.jpeg', alt: '绿白分镜4'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5ec1ec39a_1754160833.jpeg" alt="绿白分镜2" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5ec1ec39a_1754160833.jpeg', alt: '绿白分镜2'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5ed797509_1754160855.jpeg" alt="绿白分镜5" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5ed797509_1754160855.jpeg', alt: '绿白分镜5'})"/>
                        </div>
                      </div>
                    </div>
                  </div>
                  <!-- 右侧动图区域 -->
                  <div class="lg:col-span-2">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">动态示意</span>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-full min-h-[20rem]">
                      <img src="https://pic1.imgdb.cn/item/688eec1d58cb8da5c8ffc7f1.gif" alt="绿白动态帧" class="w-full h-full object-contain" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688eec1d58cb8da5c8ffc7f1.gif', alt: '绿白动态帧'})"/>
                    </div>
                  </div>
                </div>
              </div>

              <!-- 红白配色：东西方融合版画风 -->
              <div class="space-y-6">
                <h5 class="text-xl font-semibold text-white">红白配色：东西方融合版画风</h5>
                <div class="grid grid-cols-1 lg:grid-cols-5 gap-6">
                  <!-- 左侧静态图片区域 -->
                  <div class="lg:col-span-3">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">分镜示意</span>
                    </div>
                    <div class="grid grid-cols-3 gap-3 h-full">
                      <!-- 第一行 Z字形布局: 1 → 2 → 3 -->
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688eeccae52cd_1754197194.jpeg" alt="红白风格定调" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688eeccae52cd_1754197194.jpeg', alt: '红白风格定调'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688eecff10f2a_1754197247.jpeg" alt="红白分镜3" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688eecff10f2a_1754197247.jpeg', alt: '红白分镜3'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef2c85bd30_1754198728.jpeg" alt="红白分镜6" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef2c85bd30_1754198728.jpeg', alt: '红白分镜6'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688eece76f7bd_1754197223.jpeg" alt="红白分镜1" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688eece76f7bd_1754197223.jpeg', alt: '红白分镜1'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef230e35d6_1754198576.jpeg" alt="红白分镜4" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef230e35d6_1754198576.jpeg', alt: '红白分镜4'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef25d94cdb_1754198621.jpeg" alt="红白分镜7" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef25d94cdb_1754198621.jpeg', alt: '红白分镜7'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef2157154a_1754198549.jpeg" alt="红白分镜2" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef2157154a_1754198549.jpeg', alt: '红白分镜2'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef2bc56b81_1754198716.jpeg" alt="红白分镜5" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef2bc56b81_1754198716.jpeg', alt: '红白分镜5'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-32">
                          <img src="https://img.cdn1.vip/i/688ef3050cdb3_1754198789.jpeg" alt="红白分镜8" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688ef3050cdb3_1754198789.jpeg', alt: '红白分镜8'})"/>
                        </div>
                      </div>
                    </div>
                  </div>
                  <!-- 右侧动图区域 -->
                  <div class="lg:col-span-2">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">动态示意</span>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-full min-h-[20rem]">
                      <img src="https://pic1.imgdb.cn/item/688efb6058cb8da5c8fff2ee.gif" alt="红白动态帧" class="w-full h-full object-contain" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688efb6058cb8da5c8fff2ee.gif', alt: '红白动态帧'})"/>
                    </div>
                  </div>
                </div>
              </div>

              <!-- 紫色配色：现代扁平插画风 -->
              <div class="space-y-6">
                <h5 class="text-xl font-semibold text-white">紫色配色：现代扁平插画风</h5>
                <div class="grid grid-cols-1 lg:grid-cols-5 gap-6">
                  <!-- 左侧静态图片区域 -->
                  <div class="lg:col-span-3">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">分镜示意</span>
                    </div>
                    <div class="grid grid-cols-3 gap-3 h-full">
                      <!-- 第一行 -->
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e51dd5fe0f_1754157533.jpeg" alt="紫色风格定调" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e51dd5fe0f_1754157533.jpeg', alt: '紫色风格定调'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e52110cf69_1754157585.jpeg" alt="紫色分镜1" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e52110cf69_1754157585.jpeg', alt: '紫色分镜1'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e51fceb24e_1754157564.jpeg" alt="紫色分镜2" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e51fceb24e_1754157564.jpeg', alt: '紫色分镜2'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e51ffb028b_1754157567.jpeg" alt="紫色分镜3" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e51ffb028b_1754157567.jpeg', alt: '紫色分镜3'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5201d473a_1754157569.jpeg" alt="紫色分镜4" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5201d473a_1754157569.jpeg', alt: '紫色分镜4'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5204c448a_1754157572.jpeg" alt="紫色分镜5" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5204c448a_1754157572.jpeg', alt: '紫色分镜5'})"/>
                        </div>
                      </div>
                    </div>
                  </div>
                  <!-- 右侧动图区域 -->
                  <div class="lg:col-span-2">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">动态示意</span>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-full min-h-[20rem]">
                      <img src="https://pic1.imgdb.cn/item/688e514758cb8da5c8ff414d.gif" alt="紫色动态帧" class="w-full h-full object-contain" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688e514758cb8da5c8ff414d.gif', alt: '紫色动态帧'})"/>
                    </div>
                  </div>
                </div>
              </div>

              <!-- 蓝色配色：梵高油画风 -->
              <div class="space-y-6">
                <h5 class="text-xl font-semibold text-white">蓝色配色：梵高油画风</h5>
                <div class="grid grid-cols-1 lg:grid-cols-5 gap-6">
                  <!-- 左侧静态图片区域 -->
                  <div class="lg:col-span-3">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">分镜示意</span>
                    </div>
                    <div class="grid grid-cols-3 gap-3 h-full">
                      <!-- 第一行 -->
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d8792082_1754160519.jpeg" alt="蓝色分镜1" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d8792082_1754160519.jpeg', alt: '蓝色分镜1'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d9393b9a_1754160531.jpeg" alt="蓝色分镜4" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d9393b9a_1754160531.jpeg', alt: '蓝色分镜4'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d8e95eab_1754160526.jpeg" alt="蓝色分镜2" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d8e95eab_1754160526.jpeg', alt: '蓝色分镜2'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d9c61cfd_1754160540.jpeg" alt="蓝色分镜5" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d9c61cfd_1754160540.jpeg', alt: '蓝色分镜5'})"/>
                        </div>
                      </div>
                      <div class="space-y-3">
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d921adf0_1754160530.jpeg" alt="蓝色分镜3" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d921adf0_1754160530.jpeg', alt: '蓝色分镜3'})"/>
                        </div>
                        <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-40">
                          <img src="https://img.cdn1.vip/i/688e5d9f29c6e_1754160543.jpeg" alt="蓝色分镜6" class="w-full h-full object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688e5d9f29c6e_1754160543.jpeg', alt: '蓝色分镜6'})"/>
                        </div>
                      </div>
                    </div>
                  </div>
                  <!-- 右侧动图区域 -->
                  <div class="lg:col-span-2">
                    <div class="mb-2">
                      <span class="text-sm text-gray-400 bg-gray-800 bg-opacity-60 px-3 py-1 rounded-full">动态示意</span>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform h-full min-h-[20rem]">
                      <img src="https://pic1.imgdb.cn/item/688e573a58cb8da5c8ff47a4.gif" alt="蓝色动态帧" class="w-full h-full object-contain" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688e573a58cb8da5c8ff47a4.gif', alt: '蓝色动态帧'})"/>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Chapter 3 -->
    <div class="py-20 px-8 bg-gradient-to-br from-black via-gray-900 to-purple-900">
      <div class="max-w-7xl mx-auto">
        <!-- 章节标题 -->
        <div class="text-center mb-16">
          <h2 class="text-5xl font-bold mb-6">
            <span class="text-white">Chapter 3</span>
            <span class="text-green-400"> 风格美学：定义和创造新风格</span>
          </h2>
          <p class="text-2xl text-gray-400">Style Aesthetics: Defining & Creating New Visual Languages</p>
        </div>
        
        <!-- 项目5 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 mb-12 animate-on-scroll" data-animation="fadeInLeft">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 5：</span>万圣节节日投影风格设计
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              从0到1构建节日主题特效贴纸包：万圣节风格LoRA模型训练与应用
            </h4>
            
            <!-- 项目思考 -->
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-12">
              <div class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30">
                <h6 class="text-xl font-bold mb-4 text-green-400">The Goal</h6>
                <p class="text-gray-300 leading-relaxed">
                  为投影产品快速、批量地生成高质量、风格统一的万圣节贴纸内容。
                </p>
              </div>
              <div class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30">
                <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                <p class="text-gray-300 leading-relaxed">
                  收集数据并训练了三款主题LoRA模型（霓虹灯艺术、暗黑幻想、粒子梦幻），保证风格的独特性和一致性。并基于这三款模型，构建了包含背景、元素、的'万圣节特效素材库'，设计师可以直接调用，极大提升内容生产效率。
                </p>
              </div>
            </div>
            
            <!-- 风格展示区域 -->
            <div class="space-y-16 mb-12">
              <!-- 风格一：霓虹灯艺术风格 -->
              <div class="space-y-8">
                <h5 class="text-2xl font-semibold text-green-400">风格一：霓虹灯艺术风格</h5>
                
                <!-- 背景展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">背景素材</h6>
                  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img src="https://img.cdn1.vip/i/688efd81a66fe_1754201473.jpeg" alt="霓虹背景1" class="w-full h-48 object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688efd81a66fe_1754201473.jpeg', alt: '霓虹背景1'})"/>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img src="https://img.cdn1.vip/i/688efd80b677b_1754201472.jpeg" alt="霓虹背景2" class="w-full h-48 object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688efd80b677b_1754201472.jpeg', alt: '霓虹背景2'})"/>
                    </div>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img src="https://img.cdn1.vip/i/688efd7f8655d_1754201471.jpeg" alt="霓虹背景3" class="w-full h-48 object-cover" @click="openImageModal({url: 'https://img.cdn1.vip/i/688efd7f8655d_1754201471.jpeg', alt: '霓虹背景3'})"/>
                    </div>
                  </div>
                </div>
                
                <!-- 元素展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">设计元素</h6>
                  <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                    <div v-for="(element, index) in neonElements" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="element.url" :alt="element.alt" class="w-full h-32 object-cover" @click="openImageModal(element)"/>
                    </div>
                  </div>
                </div>
                
                <!-- 应用效果 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">应用效果</h6>
                  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div v-for="(effect, index) in neonEffects" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="effect.url" :alt="effect.alt" class="w-full h-48 object-cover" @click="openImageModal(effect)"/>
                    </div>
                  </div>
                </div>
              </div>
              
              <!-- 风格二：暗黑幻想风格 -->
              <div class="space-y-8">
                <h5 class="text-2xl font-semibold text-green-400">风格二：暗黑幻想风格</h5>
                
                <!-- 背景展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">背景素材</h6>
                  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div v-for="(bg, index) in darkFantasyBgs" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="bg.url" :alt="bg.alt" class="w-full h-48 object-cover" @click="openImageModal(bg)"/>
                    </div>
                  </div>
                </div>
                
                <!-- 元素展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">设计元素</h6>
                  <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                    <div v-for="(element, index) in darkFantasyElements" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="element.url" :alt="element.alt" class="w-full h-32 object-cover" @click="openImageModal(element)"/>
                    </div>
                  </div>
                </div>
                
                <!-- 关键帧应用和动态帧 -->
                <div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
                  <div class="lg:col-span-2 space-y-4">
                    <h6 class="text-lg font-medium text-white">关键帧应用</h6>
                    <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
                      <div v-for="(frame, index) in darkFantasyFrames" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                        <img :src="frame.url" :alt="frame.alt" class="w-full h-32 object-cover" @click="openImageModal(frame)"/>
                      </div>
                    </div>
                  </div>
                  <div class="space-y-4">
                    <h6 class="text-lg font-medium text-white">动态帧示意</h6>
                    <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img src="https://pic1.imgdb.cn/item/688f016f58cb8da5c8fff935.gif" alt="暗黑幻想动态帧" class="w-full h-48 object-contain" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688f016f58cb8da5c8fff935.gif', alt: '暗黑幻想动态帧'})"/>
                    </div>
                  </div>
                </div>
              </div>
              
              <!-- 风格三：粒子梦幻风格 -->
              <div class="space-y-8">
                <h5 class="text-2xl font-semibold text-green-400">风格三：粒子梦幻风格</h5>
                
                <!-- 背景展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">背景素材</h6>
                  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
                    <div v-for="(bg, index) in particleDreamBgs" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="bg.url" :alt="bg.alt" class="w-full h-48 object-cover" @click="openImageModal(bg)"/>
                    </div>
                  </div>
                </div>
                
                <!-- 元素展示 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">设计元素</h6>
                  <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-4">
                    <div v-for="(element, index) in particleDreamElements" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="element.url" :alt="element.alt" class="w-full h-32 object-cover" @click="openImageModal(element)"/>
                    </div>
                  </div>
                </div>
                
                <!-- 应用效果 -->
                <div class="space-y-4">
                  <h6 class="text-lg font-medium text-white">应用效果</h6>
                  <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-5 gap-6">
                    <div v-for="(effect, index) in particleDreamEffects" :key="index" class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform">
                      <img :src="effect.url" :alt="effect.alt" class="w-full h-48 object-cover" @click="openImageModal(effect)"/>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <!-- 项目6 -->
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20 animate-on-scroll" data-animation="fadeInRight">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 6：</span>狼人杀卡片角色设计
          </h3>
          <div class="mb-12">
            <h4 class="text-2xl font-semibold mb-6 text-green-400">
              风格融合实验：日式动漫 x 欧洲复古插画
            </h4>
            
            <!-- 项目思考 -->
            <div class="mb-12">
              <div class="bg-gradient-to-br from-green-900 to-black p-8 rounded-2xl border border-green-400 border-opacity-30">
                <h6 class="text-xl font-bold mb-4 text-green-400">My Method</h6>
                <p class="text-gray-300 leading-relaxed">
                  探索不同文化风格碰撞，通过Midjourney的Blend和精准的提示词工程，将两种看似无关的风格（日式动漫的人物动态和欧洲复古插画的笔触质感）进行融合，创造出一种全新的、具有叙事感的视觉语言，并用--sref进行控制产出一系列角色设计。
                </p>
              </div>
            </div>
            
            <!-- 角色卡片展示 -->
            <div class="space-y-8">
              <h5 class="text-xl font-semibold text-white">角色设计展示</h5>
              
              <!-- 牌背设计和角色卡片一整行展示 -->
              <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-8 gap-4">
                <!-- 牌背设计 -->
                <div class="space-y-2 animate-on-scroll" data-animation="fadeInLeft">
                  <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 hover:shadow-2xl hover:shadow-green-400/30 transition-all duration-300 transform hover:-translate-y-2">
                    <img src="https://pic1.imgdb.cn/item/688f07e358cb8da5c8000a28.png" alt="狼人杀牌背设计" class="w-full h-auto object-cover" @click="openImageModal({url: 'https://pic1.imgdb.cn/item/688f07e358cb8da5c8000a28.png', alt: '狼人杀牌背设计'})"/>
                  </div>
                  <p class="text-center text-sm text-gray-300">牌背</p>
                </div>
                
                <!-- 角色卡片 -->
                <div v-for="(card, index) in werewolfCards" :key="index" class="space-y-2 animate-on-scroll" data-animation="fadeInUp" :style="{ animationDelay: `${(index + 1) * 0.15}s` }">
                  <div class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 hover:shadow-2xl hover:shadow-green-400/30 transition-all duration-300 transform hover:-translate-y-2">
                    <img :src="card.url" :alt="card.alt" class="w-full h-auto object-cover" @click="openImageModal(card)"/>
                  </div>
                  <p class="text-center text-sm text-gray-300">{{ card.name }}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Thanks 封底 -->
    <div
      class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-black via-gray-900 to-green-900"
    >
      <div
        class="absolute inset-0 bg-cover bg-center opacity-30"
        :style="{
          backgroundImage:
            'url(https://readdy.ai/api/search-image?query=elegant%20minimalist%20digital%20art%20background%20with%20flowing%20green%20light%20trails%20and%20abstract%20geometric%20patterns%20creating%20a%20sophisticated%20finale%20atmosphere%20for%20design%20portfolio%20conclusion%20with%20dark%20gradient%20overlay&width=1440&height=1024&seq=thanks-bg-002&orientation=landscape)',
        }"
      ></div>
      <div class="relative z-10 text-center max-w-5xl mx-auto px-8">
        <h1 class="text-9xl font-bold mb-12 tracking-wider">
          <span class="text-white">Thank</span><span class="text-green-400">s</span>
        </h1>
        <div
          class="bg-black bg-opacity-60 backdrop-blur-sm rounded-3xl p-16 border border-green-400 border-opacity-30"
        >
          <div class="mb-12">
            <h2 class="text-4xl font-bold mb-6 text-green-400">感谢您的观看</h2>
            <p class="text-2xl text-gray-300 leading-relaxed">期待与您探讨更多 AIGC 设计的可能性</p>
          </div>
          <div class="space-y-8 mb-12">
            <div class="flex items-center justify-center gap-8">
              <div class="flex items-center">
                <i class="fas fa-phone text-green-400 mr-4 text-2xl"></i>
                <span class="text-xl text-gray-300">18784308516</span>
              </div>
              <div class="flex items-center">
                <i class="fas fa-envelope text-green-400 mr-4 text-2xl"></i>
                <span class="text-xl text-gray-300">1010829601@qq.com</span>
              </div>
              <div class="flex items-center">
                <i class="fas fa-location-dot text-green-400 mr-4 text-2xl"></i>
                <span class="text-xl text-gray-300">Base in 深圳</span>
              </div>
            </div>
          </div>
          <div class="border-t border-green-400 border-opacity-30 pt-8">
            <p class="text-lg text-gray-400">
              &copy; 2025 朱锐 Zero Portfolio. All rights reserved.
            </p>
          </div>
        </div>
      </div>
    </div>
    <!-- 图片模态框 -->
    <div
      v-if="showModal"
      class="fixed inset-0 bg-black bg-opacity-90 z-50 flex items-center justify-center p-8"
      @click="closeImageModal"
    >
      <div class="relative max-w-4xl max-h-full">
        <button
          @click="closeImageModal"
          class="absolute -top-12 right-0 text-white text-2xl hover:text-green-400 cursor-pointer"
        >
          <i class="fas fa-times"></i>
        </button>
        <img
          :src="selectedImage?.url"
          :alt="selectedImage?.alt"
          class="max-w-full max-h-full object-contain rounded-xl"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
  import { ref, onMounted, onUnmounted } from 'vue';
  
  const showModal = ref(false);
  const selectedImage = ref(null);
  
  // 动态交互状态
  const cursor = ref<HTMLElement | null>(null);
  
  // 丝滑光标系统
  const cursorPos = ref({ x: 0, y: 0 });
  const targetPos = ref({ x: 0, y: 0 });
  const trailElements = [];
  const sparkleElements = [];
  const trailPositions = [];
  let animationId;
  let lastSparkleTime = 0;
  
  // 缓动函数
  const lerp = (start, end, factor) => {
    return start + (end - start) * factor;
  };
  
  // 计算速度
  let lastMousePos = { x: 0, y: 0 };
  let mouseVelocity = { x: 0, y: 0 };
  
  // 鼠标跟随粒子效果
  const updateCursor = (e) => {
    targetPos.value.x = e.clientX;
    targetPos.value.y = e.clientY;
    
    // 计算鼠标速度
    mouseVelocity.x = e.clientX - lastMousePos.x;
    mouseVelocity.y = e.clientY - lastMousePos.y;
    lastMousePos.x = e.clientX;
    lastMousePos.y = e.clientY;
  };
  
  // 丝滑动画循环
  const smoothAnimation = () => {
    // 主光标平滑跟随
    cursorPos.value.x = lerp(cursorPos.value.x, targetPos.value.x, 0.15);
    cursorPos.value.y = lerp(cursorPos.value.y, targetPos.value.y, 0.15);
    
    if (cursor.value) {
      const speed = Math.sqrt(mouseVelocity.x ** 2 + mouseVelocity.y ** 2);
      const motionBlur = Math.min(speed * 0.3, 8);
      
      cursor.value.style.left = cursorPos.value.x + 'px';
      cursor.value.style.top = cursorPos.value.y + 'px';
      cursor.value.style.filter = `blur(${motionBlur * 0.1}px)`;
    }
    
    // 更新拖尾粒子位置（更自然的跟随）
    trailElements.forEach((trail, index) => {
      if (!trailPositions[index]) {
        trailPositions[index] = { 
          x: cursorPos.value.x, 
          y: cursorPos.value.y, 
          vx: 0, 
          vy: 0 
        };
      }
      
      const pos = trailPositions[index];
      const delay = (index + 1) * 0.08; // 延迟系数
      const spring = 0.12 - delay * 0.005; // 弹性系数
      const damping = 0.85; // 阻尼系数
      
      // 弹性动画
      const dx = cursorPos.value.x - pos.x;
      const dy = cursorPos.value.y - pos.y;
      
      pos.vx += dx * spring;
      pos.vy += dy * spring;
      pos.vx *= damping;
      pos.vy *= damping;
      
      pos.x += pos.vx;
      pos.y += pos.vy;
      
      // 运动模糊
      const trailSpeed = Math.sqrt(pos.vx ** 2 + pos.vy ** 2);
      const blur = Math.min(trailSpeed * 0.2 + index * 0.3, 4);
      
      trail.style.left = pos.x + 'px';
      trail.style.top = pos.y + 'px';
      trail.style.filter = `blur(${blur}px)`;
    });
    
    // 飘散光斑粒子效果（降低频率，减少干扰）
    const now = Date.now();
    const speed = Math.sqrt(mouseVelocity.x ** 2 + mouseVelocity.y ** 2);
    if (now - lastSparkleTime > 120 && speed > 5) { // 每120ms且快速移动时才创建光斑
      createSparkle();
      lastSparkleTime = now;
    }
    
    // 更新现有光斑
    updateSparkles();
    
    animationId = requestAnimationFrame(smoothAnimation);
  };
  
  // 创建飘散光斑（沿轨迹方向）
  const createSparkle = () => {
    const speed = Math.sqrt(mouseVelocity.x ** 2 + mouseVelocity.y ** 2);
    if (speed < 5) return; // 提高触发门槛
    
    const availableSparkle = sparkleElements.find(el => el.style.opacity === '0');
    if (availableSparkle) {
      // 计算运动方向
      const moveAngle = Math.atan2(mouseVelocity.y, mouseVelocity.x);
      // 在运动方向的垂直方向上添加小幅随机偏移
      const perpAngle = moveAngle + Math.PI / 2;
      const offsetDistance = (Math.random() - 0.5) * 15; // 减小偏移范围
      
      const sparkleX = cursorPos.value.x + Math.cos(perpAngle) * offsetDistance;
      const sparkleY = cursorPos.value.y + Math.sin(perpAngle) * offsetDistance;
      
      availableSparkle.style.left = sparkleX + 'px';
      availableSparkle.style.top = sparkleY + 'px';
      availableSparkle.style.opacity = '0.3'; // 降低初始透明度
      availableSparkle.style.transform = 'translate(-50%, -50%) scale(0.8)';
      
      // 沿运动轨迹的反方向飘散
      const driftX = -mouseVelocity.x * 0.3 + (Math.random() - 0.5) * 10;
      const driftY = -mouseVelocity.y * 0.3 + (Math.random() - 0.5) * 10;
      
      // 设置更细腻的飘散动画
      availableSparkle.animate([
        { 
          opacity: '0.3', 
          transform: 'translate(-50%, -50%) scale(0.8)',
          filter: 'blur(0.2px)'
        },
        { 
          opacity: '0', 
          transform: `translate(-50%, -50%) scale(0.2) translate(${driftX}px, ${driftY}px)`,
          filter: 'blur(1px)'
        }
      ], {
        duration: 600 + Math.random() * 300, // 缩短动画时间
        easing: 'cubic-bezier(0.25, 0.46, 0.45, 0.94)'
      }).onfinish = () => {
        availableSparkle.style.opacity = '0';
      };
    }
  };
  
  // 更新光斑粒子
  const updateSparkles = () => {
    // 这个函数主要用于处理动画完成后的清理
    // 大部分工作由Web Animations API处理
  };
  
  // 粒子样式生成
  const getParticleStyle = (index) => {
    const size = Math.random() * 4 + 1;
    const x = Math.random() * 100;
    const y = Math.random() * 100;
    const animationDelay = Math.random() * 20;
    const animationDuration = Math.random() * 10 + 10;
    
    return {
      width: `${size}px`,
      height: `${size}px`,
      left: `${x}%`,
      top: `${y}%`,
      animationDelay: `${animationDelay}s`,
      animationDuration: `${animationDuration}s`,
    };
  };
  
  // 滚动动画观察器
  const initScrollAnimations = () => {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const animation = entry.target.getAttribute('data-animation');
          entry.target.classList.add('animate-in', animation || 'fadeInUp');
        }
      });
    }, { threshold: 0.1 });
    
    document.querySelectorAll('.animate-on-scroll').forEach((el) => {
      observer.observe(el);
    });
  };
  

  const koreanStyleImages = [
    { url: 'https://img.cdn1.vip/i/688e267929ebf_1754146425.jpeg', alt: '韩风1' },
    { url: 'https://img.cdn1.vip/i/688e266d22c81_1754146413.jpeg', alt: '韩风2' },
    { url: 'https://img.cdn1.vip/i/688e266f044ec_1754146415.jpeg', alt: '韩风3' },
    { url: 'https://img.cdn1.vip/i/688e266e5adb2_1754146414.jpeg', alt: '韩风4' },
  ];
  const posterImages = [
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/2372dc00ce8fcbf9482134a699f3117b.png',
      alt: '创意海报1',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/7b7cd3d5c475781d7be8b0e8b9db5311.png',
      alt: '创意海报3',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/4701cec4a9c9b460f15a8fc431360488.png',
      alt: '创意海报4',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/f010ed73e129218de689c3943802f459.png',
      alt: '创意海报5',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/9c33a6d95095a7c3a3815d6a9f2fcb3f.png',
      alt: '创意海报6',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/b33522dde5c61619d37cb733979edfee.png',
      alt: '创意海报7',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/bbafc8ae0690cb9fc658186b2bb99255.png',
      alt: '创意海报8',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/d4a119ca136f6555489528128ae10dc6.png',
      alt: '创意海报9',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/7d44369a12faead8f57407f4cd3cddcb.png',
      alt: '创意海报10',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/12860d6111326290458bc5c04a4f546f.png',
      alt: '创意海报11',
    },
    {
      url: 'https://static.readdy.ai/image/b1272b1ab6637be948241a67e27cd463/7408980526bcc862010a6089014898dc.png',
      alt: '创意海报12',
    },
    {
      url: 'https://img.cdn1.vip/i/688e18240ce77_1754142756.jpeg',
      alt: '创意海报15',
    },
    {
      url: 'https://img.cdn1.vip/i/688e182c0f322_1754142764.jpeg',
      alt: '创意海报17',
    },
    {
      url: 'https://img.cdn1.vip/i/688e182b67660_1754142763.jpeg',
      alt: '创意海报18',
    },
    {
      url: 'https://img.cdn1.vip/i/688e1899cd53a_1754142873.jpeg',
      alt: '创意海报19',
    },
    {
      url: 'https://img.cdn1.vip/i/688e189b16c35_1754142875.jpeg',
      alt: '创意海报20',
    },
    {
      url: 'https://img.cdn1.vip/i/688e189985822_1754142873.jpeg',
      alt: '创意海报21',
    },
    {
      url: 'https://img.cdn1.vip/i/688e1a50082aa_1754143312.jpeg',
      alt: '创意海报22',
    },
  ];

  // Chapter 3 图片数据
  
  // 霓虹灯艺术风格元素
  const neonElements = [
    { url: 'https://img.cdn1.vip/i/688f02ae75e9f_1754202798.jpeg', alt: '霓虹元素1' },
    { url: 'https://img.cdn1.vip/i/688f02b79b482_1754202807.jpeg', alt: '霓虹元素2' },
    { url: 'https://img.cdn1.vip/i/688f02b92a64d_1754202809.jpeg', alt: '霓虹元素3' },
    { url: 'https://img.cdn1.vip/i/688f02ba39c8c_1754202810.jpeg', alt: '霓虹元素4' },
    { url: 'https://img.cdn1.vip/i/688f02b98d68c_1754202809.jpeg', alt: '霓虹元素5' },
    { url: 'https://pic1.imgdb.cn/item/688f030358cb8da5c8fffb4b.jpg', alt: '霓虹元素6' },
    { url: 'https://pic1.imgdb.cn/item/688f030358cb8da5c8fffb4a.jpg', alt: '霓虹元素7' },
    { url: 'https://pic1.imgdb.cn/item/688f034258cb8da5c8fffc0e.jpg', alt: '霓虹元素8' },
    { url: 'https://pic1.imgdb.cn/item/688f034258cb8da5c8fffc18.jpg', alt: '霓虹元素9' },
    { url: 'https://pic1.imgdb.cn/item/688f034258cb8da5c8fffc19.jpg', alt: '霓虹元素10' },
    { url: 'https://pic1.imgdb.cn/item/688f038258cb8da5c8fffcc0.jpg', alt: '霓虹元素11' },
    { url: 'https://pic1.imgdb.cn/item/688f038b58cb8da5c8fffce0.jpg', alt: '霓虹元素12' },
    { url: 'https://pic1.imgdb.cn/item/688f038c58cb8da5c8fffce4.jpg', alt: '霓虹元素13' },
    { url: 'https://pic1.imgdb.cn/item/688f038c58cb8da5c8fffce5.jpg', alt: '霓虹元素14' },
    { url: 'https://pic1.imgdb.cn/item/688f038c58cb8da5c8fffce6.jpg', alt: '霓虹元素15' },
    { url: 'https://pic1.imgdb.cn/item/688f03ee58cb8da5c8fffdfb.jpg', alt: '霓虹元素16' },
    { url: 'https://pic1.imgdb.cn/item/688f03ed58cb8da5c8fffdf8.jpg', alt: '霓虹元素17' },
    { url: 'https://pic1.imgdb.cn/item/688f03f558cb8da5c8fffe12.jpg', alt: '霓虹元素18' },
    { url: 'https://pic1.imgdb.cn/item/688f03f658cb8da5c8fffe15.jpg', alt: '霓虹元素19' },
    { url: 'https://pic1.imgdb.cn/item/688f03f858cb8da5c8fffe1d.jpg', alt: '霓虹元素20' },
    { url: 'https://pic1.imgdb.cn/item/688f03f958cb8da5c8fffe1e.jpg', alt: '霓虹元素21' },
  ];

  // 霓虹灯艺术风格应用效果
  const neonEffects = [
    { url: 'https://i.mji.rip/2025/08/05/6d6cdfe879eec0f7e2b92651ea9e9af0.png', alt: '霓虹应用效果1' },
    { url: 'https://i.mji.rip/2025/08/05/9ec92f89eeefa5d5873abf2e6390519b.png', alt: '霓虹应用效果2' },
    { url: 'https://i.mji.rip/2025/08/05/a79e03c533dedf461b53c62b76d05a17.png', alt: '霓虹应用效果3' },
    { url: 'https://i.mji.rip/2025/08/05/64200e851356e9dc4cd44d0fc230a49e.png', alt: '霓虹应用效果4' },
  ];

  // 暗黑幻想风格背景
  const darkFantasyBgs = [
    { url: 'https://pic1.imgdb.cn/item/688f184e58cb8da5c8002c84.jpg', alt: '暗黑幻想背景1' },
    { url: 'https://pic1.imgdb.cn/item/688f187458cb8da5c8002ce1.jpg', alt: '暗黑幻想背景2' },
    { url: 'https://pic1.imgdb.cn/item/688f187458cb8da5c8002ce2.jpg', alt: '暗黑幻想背景3' },
  ];

  // 暗黑幻想风格元素
  const darkFantasyElements = [
    { url: 'https://pic1.imgdb.cn/item/688f04ac58cb8da5c8000038.jpg', alt: '暗黑幻想元素1' },
    { url: 'https://pic1.imgdb.cn/item/688f04a958cb8da5c800002e.jpg', alt: '暗黑幻想元素2' },
    { url: 'https://pic1.imgdb.cn/item/688f04b958cb8da5c800006a.jpg', alt: '暗黑幻想元素3' },
    { url: 'https://pic1.imgdb.cn/item/688f04bd58cb8da5c8000073.jpg', alt: '暗黑幻想元素4' },
    { url: 'https://pic1.imgdb.cn/item/688f04c458cb8da5c800008a.jpg', alt: '暗黑幻想元素5' },
    { url: 'https://pic1.imgdb.cn/item/688f04c958cb8da5c800009d.jpg', alt: '暗黑幻想元素6' },
    { url: 'https://pic1.imgdb.cn/item/688f05f058cb8da5c8000465.jpg', alt: '暗黑幻想元素7' },
    { url: 'https://pic1.imgdb.cn/item/688f05d858cb8da5c80003a6.jpg', alt: '暗黑幻想元素8' },
    { url: 'https://pic1.imgdb.cn/item/688f05e058cb8da5c80003e1.jpg', alt: '暗黑幻想元素9' },
    { url: 'https://pic1.imgdb.cn/item/688f05e658cb8da5c8000411.jpg', alt: '暗黑幻想元素10' },
    { url: 'https://pic1.imgdb.cn/item/688f064c58cb8da5c800065c.jpg', alt: '暗黑幻想元素11' },
  ];

  // 暗黑幻想风格关键帧
  const darkFantasyFrames = [
    { url: 'https://pic1.imgdb.cn/item/688f068958cb8da5c8000703.jpg', alt: '暗黑幻想关键帧1' },
    { url: 'https://pic1.imgdb.cn/item/688f069358cb8da5c8000717.jpg', alt: '暗黑幻想关键帧2' },
    { url: 'https://pic1.imgdb.cn/item/688f069658cb8da5c8000721.jpg', alt: '暗黑幻想关键帧3' },
    { url: 'https://pic1.imgdb.cn/item/688f06ab58cb8da5c800074c.jpg', alt: '暗黑幻想关键帧4' },
    { url: 'https://pic1.imgdb.cn/item/688f06ac58cb8da5c800074f.jpg', alt: '暗黑幻想关键帧5' },
  ];

  // 粒子梦幻风格背景
  const particleDreamBgs = [
    { url: 'https://i.mji.rip/2025/08/05/52ca6d53d2b351bbed93d096d135c417.png', alt: '粒子梦幻背景1' },
    { url: 'https://i.mji.rip/2025/08/05/5ad35a560f624004443129751d5e6250.png', alt: '粒子梦幻背景2' },
    { url: 'https://i.mji.rip/2025/08/05/dafd9ec4a6fc8a304a470b27992ba391.png', alt: '粒子梦幻背景3' },
    { url: 'https://i.mji.rip/2025/08/05/931a2637eec7b1cf77e45074751a8bfb.png', alt: '粒子梦幻背景4' },
  ];

  // 粒子梦幻风格元素
  const particleDreamElements = [
    { url: 'https://i.mji.rip/2025/08/05/757f53268689d65116843d8233614014.png', alt: '粒子梦幻元素1' },
    { url: 'https://i.mji.rip/2025/08/05/525a026cfc7207e0a10f2b289aed4017.png', alt: '粒子梦幻元素2' },
    { url: 'https://i.mji.rip/2025/08/05/e897dac6b2170e9ce5c3e3660dee0bb7.png', alt: '粒子梦幻元素3' },
    { url: 'https://i.mji.rip/2025/08/05/3d39884021b4da12b8d2326dbad548cb.png', alt: '粒子梦幻元素4' },
    { url: 'https://i.mji.rip/2025/08/05/d2fe50095c463b24054808ab032392bd.png', alt: '粒子梦幻元素5' },
  ];

  // 粒子梦幻风格应用效果
  const particleDreamEffects = [
    { url: 'https://i.mji.rip/2025/08/05/9370920c94ace9f23cd6f4c8e40bd69d.jpeg', alt: '粒子梦幻应用效果1' },
    { url: 'https://i.mji.rip/2025/08/05/15933c14bcc9a23fc7c703605d0d1255.jpeg', alt: '粒子梦幻应用效果2' },
    { url: 'https://i.mji.rip/2025/08/05/678937b10c28e345a160b1ba76b1c5f5.jpeg', alt: '粒子梦幻应用效果3' },
    { url: 'https://i.mji.rip/2025/08/05/3eb45247e98d334f6e316671b59e0844.jpeg', alt: '粒子梦幻应用效果4' },
    { url: 'https://i.mji.rip/2025/08/05/98e258091ca33b030ab44b46f57b0cb3.jpeg', alt: '粒子梦幻应用效果5' },
  ];

  // 狼人杀角色卡片
  const werewolfCards = [
    { url: 'https://pic1.imgdb.cn/item/688f07ea58cb8da5c8000a37.png', alt: '平民角色', name: '平民' },
    { url: 'https://pic1.imgdb.cn/item/688f182258cb8da5c8002c1a.png', alt: '狼人角色', name: '狼人' },
    { url: 'https://pic1.imgdb.cn/item/688f08bc58cb8da5c8000c19.png', alt: '预言家角色', name: '预言家' },
    { url: 'https://pic1.imgdb.cn/item/688f08df58cb8da5c8000c68.png', alt: '女巫角色', name: '女巫' },
    { url: 'https://pic1.imgdb.cn/item/688f08fd58cb8da5c8000cbb.png', alt: '守卫角色', name: '守卫' },
    { url: 'https://pic1.imgdb.cn/item/688f096558cb8da5c8000da1.png', alt: '猎人角色', name: '猎人' },
    { url: 'https://pic1.imgdb.cn/item/688f098e58cb8da5c8000dc8.png', alt: '警长角色', name: '警长' },
  ];
  const openImageModal = (image) => {
    selectedImage.value = image;
    showModal.value = true;
  };
  const closeImageModal = () => {
    showModal.value = false;
    selectedImage.value = null;
  };
  
  // 生命周期函数
  onMounted(() => {
    // 等待DOM渲染完成后初始化粒子系统
    setTimeout(() => {
      // 初始化拖尾粒子
      for (let i = 1; i <= 15; i++) {
        const trail = document.querySelector(`[data-trail="${i}"]`);
        if (trail) {
          trailElements.push(trail);
        }
      }
      
      // 初始化飘散光斑粒子
      for (let j = 1; j <= 15; j++) {
        const sparkle = document.querySelector(`[data-sparkle="${j}"]`);
        if (sparkle) {
          sparkleElements.push(sparkle);
        }
      }
      
      // 启动丝滑动画循环
      smoothAnimation();
    }, 100);
    
    // 初始化鼠标跟随效果
    document.addEventListener('mousemove', updateCursor);
    
    // 初始化滚动动画
    initScrollAnimations();
    
    // 为交互元素添加悬停效果（优化的版本）
    const buttons = document.querySelectorAll('button');
    buttons.forEach(button => {
      button.addEventListener('mouseenter', () => {
        if (cursor.value) {
          cursor.value.style.transform = 'translate(-50%, -50%) scale(2.5)';
          cursor.value.style.background = 'radial-gradient(circle, #22c55e 0%, #4ade80 70%)';
          cursor.value.style.boxShadow = '0 0 25px rgba(74, 222, 128, 1), 0 0 50px rgba(74, 222, 128, 0.7)';
        }
      });
      
      button.addEventListener('mouseleave', () => {
        if (cursor.value) {
          cursor.value.style.transform = 'translate(-50%, -50%) scale(1)';
          cursor.value.style.background = '#4ade80';
          cursor.value.style.boxShadow = '';
        }
      });
    });
    
    // 为卡片元素添加悬停效果
    const cards = document.querySelectorAll('.cursor-pointer');
    cards.forEach(card => {
      card.addEventListener('mouseenter', () => {
        if (cursor.value) {
          cursor.value.style.transform = 'translate(-50%, -50%) scale(1.8)';
          cursor.value.style.background = 'radial-gradient(circle, #10b981 0%, #22c55e 70%)';
        }
      });
      
      card.addEventListener('mouseleave', () => {
        if (cursor.value) {
          cursor.value.style.transform = 'translate(-50%, -50%) scale(1)';
          cursor.value.style.background = '#4ade80';
        }
      });
    });
  });
  
  onUnmounted(() => {
    document.removeEventListener('mousemove', updateCursor);
    if (animationId) {
      cancelAnimationFrame(animationId);
    }
  });
</script>

<style scoped>
  .font-sans {
    font-family:
      'Inter',
      -apple-system,
      BlinkMacSystemFont,
      'Segoe UI',
      Roboto,
      sans-serif;
  }
  .\!rounded-button {
    border-radius: 25px !important;
  }
  body {
    min-height: 1024px;
  }
  @keyframes bounce {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-25px);
    }
  }
  @keyframes spin {
    from {
      transform: rotate(0deg);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @keyframes pulse {
    0%,
    100% {
      opacity: 1;
    }
    50% {
      opacity: 0.5;
    }
  }
  .animate-bounce {
    animation: bounce 2s infinite;
  }
  .animate-spin {
    animation: spin 1s linear infinite;
  }
  .animate-pulse {
    animation: pulse 2s infinite;
  }
  
  /* 动态交互样式 */
  
  /* 粒子动画 */
  .particle {
    animation: float linear infinite;
  }
  
  @keyframes float {
    0% {
      transform: translateY(100vh) translateX(0);
      opacity: 0;
    }
    10% {
      opacity: 0.2;
    }
    90% {
      opacity: 0.2;
    }
    100% {
      transform: translateY(-100vh) translateX(100px);
      opacity: 0;
    }
  }
  

  
  /* 滚动进入动画 */
  .animate-on-scroll {
    opacity: 0;
    transform: translateY(50px);
    transition: all 0.8s ease-out;
  }
  
  .animate-in {
    opacity: 1;
    transform: translateY(0);
  }
  
  .fadeInUp {
    animation: fadeInUp 0.8s ease-out forwards;
  }
  
  .fadeInLeft {
    animation: fadeInLeft 0.8s ease-out forwards;
  }
  
  .fadeInRight {
    animation: fadeInRight 0.8s ease-out forwards;
  }
  
  @keyframes fadeInUp {
    from {
      opacity: 0;
      transform: translateY(50px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  @keyframes fadeInLeft {
    from {
      opacity: 0;
      transform: translateX(-50px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  
  @keyframes fadeInRight {
    from {
      opacity: 0;
      transform: translateX(50px);
    }
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
  
  /* 增强悬停效果 */
  .hover\:shadow-green-400\/30:hover {
    box-shadow: 0 25px 50px -12px rgba(74, 222, 128, 0.3);
  }
  
  /* 自定义滚动条 */
  ::-webkit-scrollbar {
    width: 8px;
  }
  
  ::-webkit-scrollbar-track {
    background: #1f2937;
  }
  
  ::-webkit-scrollbar-thumb {
    background: #4ade80;
    border-radius: 4px;
  }
  
  ::-webkit-scrollbar-thumb:hover {
    background: #22c55e;
  }
  
  /* 图片加载动画 */
  img {
    transition: all 0.3s ease;
  }
  
  img:hover {
    filter: brightness(1.1) contrast(1.1);
  }
  
  /* 按钮增强效果 */
  button {
    position: relative;
    overflow: hidden;
  }
  
  button::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 0;
    height: 0;
    border-radius: 50%;
    background: rgba(74, 222, 128, 0.3);
    transition: width 0.6s, height 0.6s;
    transform: translate(-50%, -50%);
    z-index: 0;
  }
  
  button:hover::before {
    width: 300px;
    height: 300px;
  }
  
  button > * {
    position: relative;
    z-index: 1;
  }
  
  /* 丝滑粒子光标样式 */
  .smooth-cursor {
    box-shadow: 
      0 0 15px rgba(74, 222, 128, 1),
      0 0 30px rgba(74, 222, 128, 0.8),
      0 0 45px rgba(74, 222, 128, 0.5),
      0 0 60px rgba(74, 222, 128, 0.3);
    animation: smooth-pulse 3s ease-in-out infinite alternate;
    transition: all 0.1s cubic-bezier(0.25, 0.46, 0.45, 0.94);
    will-change: transform, filter;
  }
  
  @keyframes smooth-pulse {
    0% {
      box-shadow: 
        0 0 15px rgba(74, 222, 128, 1),
        0 0 30px rgba(74, 222, 128, 0.8),
        0 0 45px rgba(74, 222, 128, 0.5);
    }
    100% {
      box-shadow: 
        0 0 20px rgba(74, 222, 128, 1),
        0 0 40px rgba(74, 222, 128, 0.9),
        0 0 60px rgba(74, 222, 128, 0.7),
        0 0 80px rgba(74, 222, 128, 0.4);
    }
  }
  
  .smooth-trail {
    box-shadow: 
      0 0 10px rgba(74, 222, 128, 0.7),
      0 0 20px rgba(74, 222, 128, 0.5);
    transition: none;
    will-change: transform, left, top, opacity, filter;
    animation: trail-glow 2s ease-in-out infinite alternate;
  }
  
  @keyframes trail-glow {
    0% {
      box-shadow: 
        0 0 8px rgba(74, 222, 128, 0.6),
        0 0 16px rgba(74, 222, 128, 0.4);
    }
    100% {
      box-shadow: 
        0 0 12px rgba(74, 222, 128, 0.8),
        0 0 24px rgba(74, 222, 128, 0.6);
    }
  }
  
  /* 飘散光斑粒子（细腻版本） */
  .sparkle-particle {
    box-shadow: 
      0 0 2px rgba(74, 222, 128, 0.4),
      0 0 4px rgba(74, 222, 128, 0.2);
    will-change: transform, opacity, filter;
    animation: none; /* 移除默认动画，减少干扰 */
    transition: none;
  }
  
  /* 轻微的闪烁效果，仅在必要时使用 */
  @keyframes subtle-twinkle {
    0% {
      opacity: 0.1;
      transform: translate(-50%, -50%) scale(0.5);
    }
    100% {
      opacity: 0.3;
      transform: translate(-50%, -50%) scale(0.8);
    }
  }
  
  /* 运动模糊效果优化 */
  .smooth-cursor,
  .smooth-trail,
  .sparkle-particle {
    backface-visibility: hidden;
    perspective: 1000px;
    transform-style: preserve-3d;
  }
  
  /* 性能优化 */
  @media (prefers-reduced-motion: reduce) {
    .smooth-cursor,
    .smooth-trail,
    .sparkle-particle {
      animation: none;
      transition: none;
    }
  }
  
  /* 高DPI屏幕优化 */
  @media (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi) {
    .smooth-cursor {
      border-radius: 50%;
      background: radial-gradient(circle, rgba(74, 222, 128, 1) 0%, rgba(74, 222, 128, 0.8) 50%, rgba(74, 222, 128, 0.3) 100%);
    }
    
    .smooth-trail {
      border-radius: 50%;
      background: radial-gradient(circle, rgba(74, 222, 128, 0.9) 0%, rgba(74, 222, 128, 0.6) 60%, rgba(74, 222, 128, 0.2) 100%);
    }
  }
</style>

