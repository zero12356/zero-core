<!-- The exported code uses Tailwind CSS. Install Tailwind CSS in your dev environment to ensure all styles work. -->
<template>
  <div class="min-h-screen bg-black text-white font-sans">
    <!-- 封面区域 -->
    <div
      class="relative min-h-screen flex items-center justify-center bg-gradient-to-br from-black via-gray-900 to-green-900"
    >
      <div
        class="absolute inset-0 bg-cover bg-center opacity-30"
        :style="{
          backgroundImage:
            'url(https://readdy.ai/api/search-image?query=abstract%20digital%20technology%20background%20with%20flowing%20green%20light%20particles%20and%20geometric%20patterns%20creating%20a%20futuristic%20atmosphere%20perfect%20for%20AIGC%20design%20portfolio%20showcase%20with%20dark%20gradient%20overlay&width=1440&height=1024&seq=portfolio-bg-001&orientation=landscape)',
        }"
      ></div>
      <div class="relative z-10 text-center max-w-4xl mx-auto px-8">
        <h1 class="text-8xl font-bold mb-8 tracking-wider">
          <span class="text-white">Port</span><span class="text-green-400">folio</span>
        </h1>
        <div
          class="bg-black bg-opacity-60 backdrop-blur-sm rounded-2xl p-12 border border-green-400 border-opacity-30"
        >
          <h2 class="text-4xl font-bold mb-4 text-green-400">朱锐 Zero</h2>
          <p class="text-2xl mb-6 text-gray-300">AIGC 特效设计师 / AIGC 效果产品经理</p>
          <div class="flex justify-center items-center mb-8">
            <div class="bg-green-400 text-black px-4 py-2 rounded-full text-lg font-bold">
              MBTI: ENTJ
            </div>
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
            <div class="flex items-center justify-center">
              <i class="fas fa-phone text-green-400 mr-3 text-xl"></i>
              <span class="text-lg">18784308516</span>
            </div>
            <div class="flex items-center justify-center">
              <i class="fab fa-weixin text-green-400 mr-3 text-xl"></i>
              <span class="text-lg">Aprilmay_sue</span>
            </div>
          </div>
          <div class="space-y-4">
            <h3 class="text-xl font-semibold text-green-400 mb-4">个人能力标签</h3>
            <div class="flex flex-wrap justify-center gap-4">
              <div
                class="bg-gradient-to-r from-green-400 to-green-600 text-black px-6 py-3 rounded-full font-semibold cursor-pointer hover:scale-105 transition-transform !rounded-button whitespace-nowrap"
              >
                AIGC 特效落地
              </div>
              <div
                class="bg-gradient-to-r from-green-400 to-green-600 text-black px-6 py-3 rounded-full font-semibold cursor-pointer hover:scale-105 transition-transform !rounded-button whitespace-nowrap"
              >
                潮流风格创造
              </div>
              <div
                class="bg-gradient-to-r from-green-400 to-green-600 text-black px-6 py-3 rounded-full font-semibold cursor-pointer hover:scale-105 transition-transform !rounded-button whitespace-nowrap"
              >
                产品化与工程化思维
              </div>
            </div>
          </div>
        </div>
      </div>
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
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20">
          <h3 class="text-4xl font-bold mb-8 text-center">
            <span class="text-green-400">项目 2：</span>人物转绘工作流设计
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
                <div class="aspect-video overflow-hidden rounded-xl">
                  <img
                    src="https://pic1.imgdb.cn/item/688f287358cb8da5c8006bc6.png"
                    alt="ComfyUI节点图"
                    class="w-full h-full object-cover cursor-pointer"
                    @click="
                      openImageModal({
                        url: 'https://pic1.imgdb.cn/item/688f287358cb8da5c8006bc6.png',
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
                      class="aspect-square overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform"
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
                      class="overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform"
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
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20">
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
                  class="aspect-square overflow-hidden rounded-xl border border-green-400 border-opacity-30 cursor-pointer hover:scale-105 transition-transform"
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
                <div class="aspect-video overflow-hidden rounded-xl">
                  <img
                    src="https://img.cdn1.vip/i/688e1acac98e0_1754143434.jpeg"
                    alt="工作流节点截图"
                    class="w-full h-full object-cover cursor-pointer"
                    @click="
                      openImageModal({
                        url: 'https://img.cdn1.vip/i/688e1acac98e0_1754143434.jpeg',
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
        <div class="bg-gray-900 rounded-3xl p-12 border border-green-400 border-opacity-20">
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
            <div class="flex flex-col md:flex-row items-center justify-center gap-8 md:gap-12">
              <div class="flex items-center">
                <i class="fas fa-envelope text-green-400 mr-4 text-2xl"></i>
                <span class="text-xl text-gray-300">联系邮箱：zero@example.com</span>
              </div>
              <div class="flex items-center">
                <i class="fab fa-linkedin text-green-400 mr-4 text-2xl"></i>
                <span class="text-xl text-gray-300">LinkedIn：朱锐 Zero</span>
              </div>
            </div>
            <div class="flex items-center justify-center">
              <i class="fas fa-location-dot text-green-400 mr-4 text-2xl"></i>
              <span class="text-xl text-gray-300">Base in 深圳</span>
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

<script setup>
  import { ref } from 'vue';

  const showModal = ref(false);
  const selectedImage = ref(null);
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
  const openImageModal = (image) => {
    selectedImage.value = image;
    showModal.value = true;
  };
  const closeImageModal = () => {
    showModal.value = false;
    selectedImage.value = null;
  };
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
</style>
