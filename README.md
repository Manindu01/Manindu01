import React from 'react';
import { Card, CardHeader, CardTitle, CardContent } from '@/components/ui/card';
import { PieChart, Pie, Cell, Tooltip, Legend } from 'recharts';

const data = [
  { name: 'HTML', value: 73.02 },
  { name: 'TypeScript', value: 1.0 },
  { name: 'Kotlin', value: 10.01 },
  { name: 'Hack', value: 0.91 },
  { name: 'CSS', value: 7.38 },
  { name: 'Shell', value: 0.72 },
  { name: 'PHP', value: 6.39 },
  { name: 'JavaScript', value: 0.56 }
];

const COLORS = ['#FF6B6B', '#4ADEDE', '#9B59B6', '#808080', '#F7DC6F', '#2ECC71', '#3498DB', '#F4D03F'];

const GithubStats = () => {
  return (
    <Card className="w-full max-w-4xl">
      <CardHeader>
        <CardTitle>Most Used Languages</CardTitle>
      </CardHeader>
      <CardContent>
        <PieChart width={600} height={400}>
          <Pie
            data={data}
            color="#000000"
            dataKey="value"
            nameKey="name"
            cx="50%"
            cy="50%"
            outerRadius={150}
            fill="#8884d8"
          >
            {data.map((entry, index) => (
              <Cell key={`cell-${index}`} fill={COLORS[index % COLORS.length]} />
            ))}
          </Pie>
          <Tooltip />
          <Legend />
        </PieChart>
      </CardContent>
    </Card>
  );
};

export default GithubStats;
