<template>
    <div>
      <Line :data="chartData" :options="chartOptions"></Line>
    </div>
  </template>
  
  <script>
  import { Line } from 'vue-chartjs'
  import { defineComponent } from 'vue'
  import { Chart as ChartJS, Title, Tooltip, Legend, LineElement, CategoryScale, LinearScale, PointElement } from 'chart.js'
  
  ChartJS.register(Title, Tooltip, Legend, LineElement, CategoryScale, LinearScale, PointElement)
  
  export default defineComponent({
    name: 'ProgressChart',
    components: { Line },
    data() {
      return {
        chartData: {
          labels: ['Primary School', 'Middle School', 'High School', 'University', 'Postgraduate'],
          datasets: [
            {
              label: 'Academic Progress',
              backgroundColor: 'rgba(66, 165, 245, 0.2)',
              borderColor: '#42A5F5',
              pointBackgroundColor: '#42A5F5',
              pointBorderColor: '#fff',
              pointHoverBackgroundColor: '#fff',
              pointHoverBorderColor: '#42A5F5',
              data: [65, 75, 85, 95, 100]
            },
            {
              label: 'Extracurricular Activities',
              backgroundColor: 'rgba(255, 99, 132, 0.2)',
              borderColor: '#FF6384',
              pointBackgroundColor: '#FF6384',
              pointBorderColor: '#fff',
              pointHoverBackgroundColor: '#fff',
              pointHoverBorderColor: '#FF6384',
              data: [50, 60, 70, 80, 90]
            }
          ]
        },
        chartOptions: {
          responsive: true,
          maintainAspectRatio: false,
          scales: {
            y: {
              beginAtZero: true,
              title: {
                display: true,
                text: 'Score'
              }
            },
            x: {
              title: {
                display: true,
                text: 'Education Level'
              }
            }
          },
          plugins: {
            tooltip: {
              enabled: true
            },
            legend: {
              display: true,
              position: 'top'
            }
          }
        }
      }
    }
  })
  </script>
  
  <style scoped>
  div {
    height: 400px;
  }
  </style>