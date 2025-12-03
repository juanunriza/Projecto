// In-memory storage (persists during runtime, resets on redeployment)
let expenses = [];
let nextId = 1;

/**
 * Vercel Serverless Function Handler
 * Endpoint: /api/expenses
 * Methods: GET, POST
 */
export default function handler(req, res) {
  // Set CORS headers
  res.setHeader('Access-Control-Allow-Credentials', 'true');
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET,POST,OPTIONS');
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization');
  
  // Handle preflight OPTIONS request
  if (req.method === 'OPTIONS') {
    return res.status(200).end();
  }

  // GET: Retrieve all expenses
  if (req.method === 'GET') {
    return res.status(200).json({
      success: true,
      count: expenses.length,
      data: expenses
    });
  }

  // POST: Add a new expense
  if (req.method === 'POST') {
    const { amount, description, category, date } = req.body;

    // Validate required fields
    const errors = [];
    
    if (!amount) {
      errors.push('amount is required');
    } else if (isNaN(parseFloat(amount)) || parseFloat(amount) <= 0) {
      errors.push('amount must be a positive number');
    }

    if (!description || description.trim() === '') {
      errors.push('description is required');
    }

    if (!category || category.trim() === '') {
      errors.push('category is required');
    }

    if (!date) {
      errors.push('date is required');
    } else if (isNaN(Date.parse(date))) {
      errors.push('date must be a valid date format');
    }

    // Return validation errors if any
    if (errors.length > 0) {
      return res.status(400).json({
        success: false,
        message: 'Validation failed',
        errors: errors
      });
    }

    // Create new expense object
    const newExpense = {
      id: nextId++,
      amount: parseFloat(amount),
      description: description.trim(),
      category: category.trim(),
      date: new Date(date).toISOString(),
      createdAt: new Date().toISOString()
    };

    // Add to array
    expenses.push(newExpense);

    // Return success response
    return res.status(201).json({
      success: true,
      message: 'Expense added successfully',
      data: newExpense
    });
  }

  // Method not allowed
  return res.status(405).json({
    success: false,
    message: `Method ${req.method} not allowed`,
    allowedMethods: ['GET', 'POST']
  });
}
