<template>
  <card title="Tugas" />
  <paginated :rows="tugas">
    <template v-slot:row="rowProps">
      <card type="assignment" :assignment="{
        ...rowProps.item,
        href: '/tugas/' + rowProps.item.id,
      }" />
    </template>
  </paginated>
</template>

<script>
import Card from '../components/Card.vue';
import Paginated from '../components/Paginated.vue';

export default {
  name: 'Tugas',
  data() {
    return {
      tugas: [
        {
          id: 12,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 39,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 17,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 19,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 22,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 31,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 1,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 2,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 99,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 42,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
        {
          id: 55,
          judul: 'Tugas Keperawatan Dasar',
          preceptor: 'dr John Doe, SpPD',
          deadline: '2021-12-08T23:23:59.000Z',
        },
      ],
    };
  },
  components: {
    Card,
    Paginated,
  },
};
</script>
