<template>
    <!-- 홈 섹션 -->
      <section v-if="currentSection === 'home'" class="content-section">
        <h2>인기 웹소설</h2>
        <div class="novel-grid">
          <div 
            v-for="novel in popularNovels" 
            :key="novel.id"
            class="novel-card"
            @click="goToNovelDetail(novel.id)"
          >
            <div class="novel-image" @click.stop="goToNovelDetail(novel.id)">
              {{ novel.title }}
            </div>
            <h3 @click.stop="showNovelDetail(novel.id)">{{ novel.title }}</h3>
            <div class="author">작가: {{ novel.author }}</div>
            <div class="description">{{ novel.description }}</div>
            <div class="meta">
              <span class="rating">⭐ {{ novel.rating }}</span>
              <span>조회수: {{ novel.views.toLocaleString() }}</span>
              <span v-if="novel.isFree" class="price-tag free">무료</span>
              <span v-else class="price-tag paid">유료</span>
              <span v-if="novel.isLatest" class="latest-tag">신작</span>
            </div>
          </div>
        </div>
      </section>
</template>

<script>  
  import { novelsData, getGenreName } from '@/data/novels';
  
  export default {
    data() {
        return {
            novelsData,
            currentSection: 'home'
        }
    },
    computed: {
        popularNovels() {
            return [...this.novelsData]
                .sort((a, b) => b.views - a.views)
                .slice(0, 6)
        },
    }
  }
   
</script>

<style scoped>


</style>